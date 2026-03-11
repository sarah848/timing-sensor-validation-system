# System Architecture
## Timing Sensor Validation System

## 1. Purpose
The purpose of the Timing Sensor Validation System is to detect a trigger event, generate a timestamp for the event, and output the event information for validation.

This document describes the high-level architecture of the system and explains how the different subsystems interact during operation.


## 2. System Overview
The Timing Sensor Validation System is a prototype embedded system designed to detect trigger events and record when those events occur.

The system uses an Arduino Uno to monitor an input trigger, detect event occurrences, generate timestamps, and output event logs through the serial interface.

The architecture demonstrates a simple event processing pipeline that forms the foundation of timing and sensor validation systems used in embedded applications.


## 3. System Inputs and Outputs
### Inputs
- Simulated trigger input
- Break beam sensor signal

### Outputs
- Event detection message
- Event timestamp
- Serial log output for validation


## 4. High-Level Architecture
The system is composed of several functional blocks that process event data from input to output.

## Architecture Diagram
![System Architecture](../assets/diagrams/system-architecture.png)

# What the Diagram Represents
This shows the **data flow pipeline**:

Sensor Trigger
↓
Arduino Processing
↓
Event Detection
↓
Timestamp Generation
↓
Serial Output
↓
Validation

### Data Flow
The system processes events through the following sequence:

1. A trigger event occurs
2. The Arduino reads the input signal
3. Event detection logic determines whether an event has occurred
4. The system generates a timestamp
5. The event and timestamp are sent to serial output
6. The output is reviewed for validation


## 5. Subsystem Descriptions

### 5.1 Trigger Input Subsystem

The Trigger Input Subsystem provides the signal that indicates when an event has occurred.

Initially, a simulated trigger is used to validate digital input detection. Later in Phase 1, the break beam sensor will serve as the physical event trigger.

**Responsibilities:**
- Provide digital input signal to the microcontroller
- Represent a physical event occurring


### 5.2 Processing Subsystem
The Processing Subsystem is implemented by the Arduino Uno microcontroller.

The Arduino reads the input signal and executes the firmware responsible for detecting events, generating timestamps, and sending output messages.

**Responsibilities:**
- Read input signals
- Execute event detection logic
- Coordinate timing and output operations


### 5.3 Event Detection Subsystem
The Event Detection Subsystem monitors the trigger input signal and determines whether an event has occurred.

The firmware continuously checks the input pin and identifies state changes indicating a trigger event.

**Responsibilities:**
- Monitor digital input
- Detect event occurrence
- Trigger timing and logging operations


### 5.4 Timing Subsystem
The Timing Subsystem generates timestamps for detected events.

In Phase 1, timestamps are generated using the Arduino `millis()` timer, which measures elapsed time since the system started.

**Responsibilities:**
- Record event timestamps
- Associate timing information with detected events


### 5.5 Output Subsystem
The Output Subsystem sends event information to the serial interface.

This allows developers to observe system behavior and validate that events and timestamps are being recorded correctly.

**Responsibilities:**
- Display event messages
- Display timestamps
- Provide logs for testing and validation

Example output:
Event detected
Timestamp: 10543 ms


### 5.6 Validation Subsystem
The Validation Subsystem verifies that the system behaves correctly during testing.

In Phase 1, validation will be performed by reviewing serial output logs and confirming that events and timestamps are generated correctly.

**Responsibilities:**
- Review event logs
- Confirm timestamp generation
- Validate event detection behavior


## 6. System Data Flow
The system processes events through the following sequence:

1. A trigger event occurs.
2. The Arduino reads the input signal.
3. The event detection logic determines whether the signal represents a valid event.
4. The system generates a timestamp.
5. The event and timestamp are sent to the serial output.
6. The output is reviewed for validation.

## 7. Phase 1 System Boundary
Phase 1 focuses on validating the core event detection and timing pipeline.

### Included in Phase 1
- Arduino Uno setup
- Trigger input detection
- Event detection logic
- Timestamp generation
- Serial output logging
- Basic system validation

### Excluded from Phase 1
- Wireless communication
- GPS-based timing
- External storage
- Multi-sensor integration
- Automated data analysis

These features may be implemented in later project phases.

## 8. Hardware Components

| Component | Description |
|-----------|-------------|
| Arduino Uno | Microcontroller used for system processing |
| Break Beam Sensor | Sensor used for event detection |
| Jumper Wires | Used for circuit connections |
| USB Cable | Used for power and programming |

## 9. Future Architecture Expansion
Future phases may extend the system architecture to include additional components such as:

- structured event logging
- Python-based log validation
- automated analysis tools
- multi-sensor integration
- wireless telemetry

A future expanded architecture could include:

Break Beam Sensor
↓
Arduino Uno
↓
Event Detection
↓
Timestamp Generation
↓
Structured Event Log
↓
Python Validation Tool
↓
Validation Report

## 10. Summary
The Timing Sensor Validation System architecture defines a simple embedded event processing pipeline.

The system detects trigger events, generates timestamps, and outputs event logs for validation. This architecture provides the foundation for further development of more advanced sensor validation and telemetry systems.