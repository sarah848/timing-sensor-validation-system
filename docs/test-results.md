### Simulated Sensor Input Test
The break beam sensor was connected to digital pin 2 on the Arduino Uno.

When the beam was interrupted, the system printed "Event detected" to the Serial Monitor.

Repeated interruptions generated repeated event messages, confirming that the digital input detection was functioning correctly.


# Test Results
## Simulated Sensor Input Test
### Break Beam Event Detection Test
The break beam sensor system was assembled using an Arduino Uno and a mini breadboard.

### Test Procedure
1. Upload event detection firmware
2. Open the Serial Monitor
3. Interrupt the beam using a hand or object

### Expected Result
The system should print an event message when the beam is interrupted.

### Observed Result
When an object interrupted the infrared beam between the emitter and receiver, the Arduino detected the signal change and printed an event message to the Serial Monitor.
Each beam interruption produced the following message in the Serial Monitor:
Event detected

### Result
PASS – Event detection is functioning correctly.
