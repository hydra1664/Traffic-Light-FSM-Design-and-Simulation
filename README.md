# Traffic Light FSM Design and Simulation

This is a simple digital design project where I built and simulated a traffic light controller using a Finite State Machine (FSM) in Logisim Evolution. The idea was to model how real-world traffic lights work by cycling through Red, Green, and Yellow lights in a predictable sequence.

All circuit files are included in the `Circuit Files` folder. Images and videos from the simulation are in the `Images and Videos` folder.


## Overview

Traffic lights work in a fixed cycle:
- Red → Stop
- Green → Go
- Yellow → Get ready to stop

I implemented this cycle as a 3-state FSM:
- S0 = Red
- S1 = Green
- S2 = Yellow

The FSM moves to the next state on each clock pulse, and there's also a reset signal to bring the system back to the Red state.

## Circuit Design

The main parts of the circuit are:
- Clock signal (controls the state transitions)
- Reset input (brings it back to Red)
- State registers (to hold the current state)
- Combinational logic (decides the next state and outputs)

When simulated in Logisim Evolution:
- Red is ON in state S0
- Green is ON in state S1
- Yellow is ON in state S2

### Circuit Diagram
<img width="1920" height="1032" alt="Traffic Light FSM Circuit" src="https://github.com/user-attachments/assets/a9a6a9f0-95e4-41a9-98b2-ade84a940da8" />


## Inputs and Outputs

Inputs:
- Clock: moves the FSM to the next state
- Reset: forces the FSM back to Red (S0)

Outputs:
- Red light
- Green light
- Yellow light

### State Transition Table

| Current State | Reset | Next State | Red | Green | Yellow |
|---------------|-------|------------|-----|-------|--------|
| S0            | 0     | S1         | 1   | 0     | 0      |
| S1            | 0     | S2         | 0   | 1     | 0      |
| S2            | 0     | S0         | 0   | 0     | 1      |
| Any           | 1     | S0         | 1   | 0     | 0      |


## Waveform Behavior

Here’s how the outputs look when clock pulses are applied during simulation:

| Clock | State | Red | Green | Yellow |
|-------|-------|-----|-------|--------|
| ↑     | S0    | 1   | 0     | 0      |
| ↑     | S1    | 0   | 1     | 0      |
| ↑     | S2    | 0   | 0     | 1      |
| ↑     | S0    | 1   | 0     | 0      |


## Simulation Video

I also recorded the FSM running in Logisim Evolution. The video shows how the lights change with each clock tick.
https://github.com/user-attachments/assets/950a73ab-46a3-41cc-9159-df1e81905d3e

## Conclusion

This project was a fun way to practice FSM design and sequential circuits. Even though it’s a simple 3-state controller, the same idea can be extended for more complex traffic systems (like multiple intersections or pedestrian signals).  

All the source circuits are in the `Circuit Files` folder, and the images/videos of the simulation are in the `Images and Videos` folder if you want to check them out.
