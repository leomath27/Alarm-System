# Alarm System (HCS12 / Dragon12)

An interrupt-driven alarm system built for the **Dragon12 trainer board** (Motorola/Freescale **MC9S12DG256 / HCS12**).

The goal of this project is to improve responsiveness and real-time behavior by using **timer interrupts** instead of polling for time-sensitive tasks like:
- 7-segment display refreshing (prevents flicker)
- keypad scanning
- siren waveform generation
- delay timing utilities

A detailed write-up is included in the report PDF under `docs/`.

## Repository layout

- `src/` — main source code (C + assembly)
- `include/` — project headers
- `docs/` — report + notes
- `project/CodeWarrior/` — the original CodeWarrior project files (Lab4.mcp) + a copy of the sources as originally laid out
- `artifacts/` — small prebuilt files (e.g., `.s19`) kept for convenience

## What’s inside (high level)

Modules are organized around the alarm workflow and peripherals:
- **Alarm / armed state machine**: `alarm.c`, `armed.c`, `config.c`
- **User input / output**: `keyPad.c`, `switches.c`, `SegDisp.c`, `lcdDisp.c`
- **Siren / timing**: `siren.c`, `delay.c`
- **Startup + low-level**: `Start12.c`, `main.asm`, `lcd.asm`

## Building / running

This was developed with **CodeWarrior for HCS12**.

1. Open the CodeWarrior project:
   - `project/CodeWarrior/Lab4.mcp`
2. Ensure your CodeWarrior installation provides the derivative include used by the assembly:
   - `mc9s12dg256.inc` (referenced by `src/main.asm`)
3. Build and flash/run using your normal Dragon12 workflow.


## Docs

- `docs/Deep-Understanding-and-Report.pdf` — full lab/report write-up
- `docs/interrupt_notes.txt` — quick notes captured during development

