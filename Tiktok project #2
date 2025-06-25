int buttonPin = 10;
int ledPin = 6;

bool ledState = false;
bool lastButtonState = HIGH;
unsigned long lastDebounceTime = 0;
unsigned long debounceDelay = 50;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP);  // Use internal pull-up resistor
  pinMode(ledPin, OUTPUT);
}

void loop() {
  bool reading = digitalRead(buttonPin);

  if (reading != lastButtonState) {
    lastDebounceTime = millis();  // reset debounce timer
  }

  if ((millis() - lastDebounceTime) > debounceDelay) {
    // If the button state changed and is pressed:
    if (reading == LOW && lastButtonState == HIGH) {
      ledState = !ledState;  // Toggle LED state
      digitalWrite(ledPin, ledState ? HIGH : LOW);
    }
  }

  lastButtonState = reading;
}
