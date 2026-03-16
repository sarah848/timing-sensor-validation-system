## Issue #5 — Break Beam Event Detection

### Objective
Implement a system that detects when the break beam sensor is interrupted and logs the event via the Serial Monitor.

### Hardware Setup

Components used:

- Arduino Uno
- Break beam sensor (IR transmitter + receiver)
- Breadboard
- Jumper wires

Connections:

| Sensor Pin | Arduino |
|-------------|--------|
| VCC | 5V |
| GND | GND |
| Signal | Digital Pin 2 |

The sensor behaves as an **active-low sensor**:

- **HIGH** → Beam intact
- **LOW** → Beam broken (event detected)

### Implementation

The Arduino continuously reads the sensor state using `digitalRead()`.  
When the beam is broken, the system records the timestamp using `millis()`.

```cpp
int sensorPin = 2;
int sensorState = 0;

void setup() {
  Serial.begin(9600);
  pinMode(sensorPin, INPUT);
}

void loop() {
  sensorState = digitalRead(sensorPin);

  if(sensorState == LOW) {
    unsigned long timestamp = millis();

    Serial.println("Event detected");
    Serial.print("Timestamp: ");
    Serial.print(timestamp);
    Serial.println(" ms");

    delay(500);
  }
}
```

## Issue 6 Example Code 

```cpp
int sensorPin = 2;
int sensorState = 0;
int lastSensorState = HIGH;

void setup() {
  Serial.begin(9600);
  pinMode(sensorPin, INPUT_PULLUP);
}

void loop() {
  sensorState = digitalRead(sensorPin);

    if (sensorState == LOW) {
      unsigned long timestamp = millis();

      Serial.println("Event detected");
      Serial.print("Timestamp: ");
      Serial.print(timestamp);
      Serial.println(" ms");
      Serial.println();

      delay (500);

    } else {
      Serial.println("No event detected");
      Serial.println();

      delay(3000);
    }

}
