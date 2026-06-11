#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);  // Change 0x27 to your I2C address if needed

// Calibrated thresholds (midpoint between OPEN and CLOSE)
#define THUMB_OPEN_MAX   498   // (267+730)/2
#define INDEX_OPEN_MAX   633   // (548+719)/2
#define PINKY_OPEN_MAX   1130  // (830+1430)/2

bool isOpen(int val, int threshold) {
  return val < threshold;
}

void setup() {
  lcd.init();
  lcd.backlight();
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Gesture Detector");
  delay(1500);
  lcd.clear();
}

void loop() {
  int thumb = analogRead(33);
  int index = analogRead(32);
  int ring  = analogRead(25);  // unused in ILY
  int pinky = analogRead(34);

  bool thumbUp  = isOpen(thumb, THUMB_OPEN_MAX);
  bool indexUp  = isOpen(index, INDEX_OPEN_MAX);
  bool pinkyUp  = isOpen(pinky, PINKY_OPEN_MAX);

  // ILY = thumb + index + pinky open, rest closed
  bool isILY = thumbUp && indexUp && pinkyUp;

  lcd.setCursor(0, 0);
  if (isILY) {
    lcd.print("  I Love You!   ");
    lcd.setCursor(0, 1);
    lcd.print("   Gesture: ILY ");
  } else {
    lcd.print("Fingers:        ");
    lcd.setCursor(0, 1);
    // Show which fingers are up (T=thumb, I=index, P=pinky)
    lcd.print("T:");
    lcd.print(thumbUp ? "O" : "X");
    lcd.print(" I:");
    lcd.print(indexUp ? "O" : "X");
    lcd.print(" P:");
    lcd.print(pinkyUp ? "O" : "X");
    lcd.print("      ");
  }

  delay(100);
}
