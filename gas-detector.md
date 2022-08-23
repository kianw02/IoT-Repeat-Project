# IoT-Repeat-Project

int ledR = 12;
int ledG = 11;
int sound = 10;
int Gas = A5;

void setup() {
  pinMode(ledR, OUTPUT);
  pinMode(ledG, OUTPUT);
  pinMode(sound, OUTPUT);
  pinMode(Gas, INPUT);
  Serial.begin(9600);
}

void loop() {
  int analogSensor = analogRead(Gas);

  Serial.print("Pin A0: ");
  Serial.println(analogSensor);
  if (analogSensor > sensorThres)
  {
    digitalWrite(ledR, HIGH);
    digitalWrite(ledG, LOW);
    tone(sound, 1000, 200);
  }
  else
  {
    digitalWrite(ledR, LOW);
    digitalWrite(ledG, HIGH);
    noTone(sound);
  }
  delay(100);
}
