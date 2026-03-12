## Arduino Setup
Board: Arduino Uno

Development Environment:
Arduino IDE installed successfully.

Blink Test:
Uploaded the Blink example sketch to confirm board communication.

Result:
The Blink example sketch was successfully uploaded to the Arduino Uno.  
The onboard LED labeled "L" blinked at one-second intervals, confirming that the development environment, board configuration, and USB communication were working correctly.

Once uploaded, the program continued running independently of the Arduino IDE.


# Hardware Setup
## Components Used
| Component | Description |
|----------|-------------|
| Arduino Uno | Microcontroller used for processing |
| Break Beam Sensor | Used to detect beam interruptions |
| Mini Breadboard | Used for wiring connections |
| Jumper Wires | Used to connect components |


## Break Beam Sensor Wiring
The break beam sensor consists of two components:

- **Emitter** – generates the infrared beam
- **Receiver** – detects whether the beam is present

### Emitter Connections
| Wire Color | Connection |
|-----------|-----------|
| Red | 5V |
| Black | GND |

### Receiver Connections
| Wire Color | Connection |
|-----------|-----------|
| Red | 5V |
| Black | GND |
| Yellow | Arduino Pin 2 |


## Breadboard Layout
The Arduino was connected to the breadboard to distribute power and connect the sensor signal.

| Arduino Pin | Connection |
|------------|-----------|
| 5V | Breadboard power rail |
| GND | Breadboard ground rail |
| Pin 2 | Break beam receiver signal |

### System Wiring
## Wiring Diagram
![Breadboard Wiring](../assets/images/timing-sensor-hardware-setup.JPG)

The break beam emitter and receiver are positioned facing each other to form an infrared beam across the test area.
The receiver output is connected to Arduino digital pin 2 through the breadboard. When the beam is interrupted, the receiver signal changes state and the Arduino detects an event.
Both sensor modules are powered using the Arduino 5V and GND rails distributed through the breadboard.

## Hardware Setup
The following image shows the wiring used for the timing sensor validation prototype.
The system consists of an Arduino Uno connected to a break beam sensor through a mini breadboard.
![Timing Sensor Hardware Setup](../assets/images/timing-sensor-hardware-setup.JPG)

## Notes
- Both emitter and receiver must receive power.
- The emitter and receiver must face each other so that the infrared beam is aligned.
- When the beam is interrupted, the receiver changes its output signal, triggering an event in the Arduino program.