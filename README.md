# Pong - TTL Digital Systems Project

A hardware Pong-style game built with discrete TTL logic. The ball is represented by one active LED moving across an eight-LED display. A correctly timed racket press reverses its direction; an early or missed hit ends the game, and Reset starts a new round.

Developed for the **Digital Systems Laboratory, ECE NTUA (2025-26)**.

## Design

`LM555 clock -> 74191 up/down counter -> 74155 decoder -> 8-LED display`

The control block uses D flip-flops and NAND/NOR/NOT logic to store direction, detect valid hits and latch the failure state. The project was developed incrementally on breadboard, verified in Logisim Evolution and integrated on perfboard.

## Repository contents

| File | Description |
| --- | --- |
| `Lab1-Clock.PDF` | Adjustable LM555 astable clock design and measurements |
| `Lab2-Display.pdf` | Active-low 74155 decoder and LED display |
| `Lab3-Display.pdf` | 74191 counter integration and completed display hardware |
| `Lab4-SoftwareSim.pdf` | Display-board modeling and waveform tests in Logisim |
| `Lab5-SoftwareSim.pdf` | Control FSM, hit/failure logic and timing simulations |
| `Lab6-Final.pdf` | Final TTL control-block implementation and integration |
| `display_logisim_simul.circ` | Logisim model of the display datapath |

## Run the simulation

Open `display_logisim_simul.circ` in **Logisim Evolution 4.2.0dev** or a compatible version containing the 74191 and 74155 TTL components.

1. Set `DEC/EN = 0` and `CNT/EN = 0`.
2. Pulse `LOAD` low to initialize the counter, then return it high.
3. Set `U/D = 0` to count up or `U/D = 1` to count down.
4. Enable clock ticks and observe the active LED and oscilloscope traces.

The supplied circuit simulates the display subsystem; the complete control logic and physical implementation are documented in Labs 5 and 6.

## Authors

Adam Moudrikah and Konstantinos Chatzipapas
