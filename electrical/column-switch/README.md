# GM Column Ignition Switch

## Overview

Standard GM column-mounted ignition switch used on this CJ5. The switch body
mounts to the steering column and is actuated by the ignition lock cylinder
via a rod. It is not the lock cylinder itself — it is the electrical switch
behind it.

## Photos

- `American Motors - US105.png` — US105 ignition switch reference diagram
- `switch-connector-face.jpg` — connector face showing pin labels
- `switch-connector-annotated.jpg` — annotated pin layout
- `switch-installed.jpg` — switch installed on column with wiring
- `pigtail-pico5659.jpg` — Pico 5659 pigtail connector reference

## Pin-Out

8x 0.25" (1/4") male blade terminals plus one 0.31" (5/16") terminal (I-3).

| Pin | Always-On | ACC | IGN/RUN | CRANK | Notes |
|-----|-----------|-----|---------|-------|-------|
| B-1 | ✓ | | | | Battery supply. B1 and B2 are internally jumped |
| B-2 | ✓ | | | | Battery supply. Jumped to B1, allows higher current via two wires |
| B-3 | ✓ | | | | Battery supply via separate circuit from B1/B2 |
| A   | | ✓ | ✓ | | Accessory — radio, wipers. Live in ACC and RUN |
| I-1 | | | ✓ | ✓ | IGN 1 — ignition devices, live in RUN and CRANK |
| I-3 | | ✓ | ✓ | | IGN 3 — HVAC/heater blower. 5/16" terminal. Powered from B3 only |
| S   | | | | ✓ | Starter solenoid trigger. Live in CRANK only |
| G-1 | | | | ✓ | Grounds to bracket in CRANK only — bulb check for oil pressure light |
| G-2 | | | | ✓ | Grounds to bracket in CRANK only — bulb check for temp light |

**G-1 and G-2 note:** Only use if running warning lights (bulbs). Do not use
if running gauges — these ground the warning light circuits for bulb check
during crank only.

## Key Position Summary

| Position | Active Pins |
|----------|-------------|
| OFF      | B1, B2, B3 only (always hot, no outputs) |
| ACC      | A, I-3 |
| RUN      | A, I-1, I-3 |
| CRANK    | I-1, S, G-1, G-2 |

## Integration With Relay System

In this build the column switch is **not used** for ignition. The ignition
switch relocated to dash is Standard Ignition US105. The column switch
connector is disconnected.

If re-integrating the column switch in future:
- B1/B2 → battery positive (fused)
- B3 → battery positive (separate fused circuit if running HVAC)
- A → ACC relay coil trigger (pin 86)
- I-1 → IGN/RUN relay coil trigger (pin 86)
- S → starter solenoid S terminal (if using column switch for start)
- I-3 → HVAC blower if installed
- G1/G2 → leave unconnected (no warning bulb circuits on this build)

## Connector / Pigtail

Two connectors mate to this switch:

**Main connector (positions 1-4 and 1-5):**
- [Duralast 263](https://www.autozone.com/p/duralast-ignition-switch-connector-263/524614) — AutoZone
- [Pico 5659PT](https://www.summitracing.com/parts/pco-5659pt) — Summit Racing.
  10, 12, and 20 AWG wire leads. Not weather-resistant. Sold individually.

The gray connector in photos is the smaller 4-pin section; the larger
connector covers the remaining terminals.

## Fusible Links

GM factory practice uses 14 AWG fusible links on B1 and B3 feeds. If not
running HVAC, B3 can drop to 16 AWG fusible link. Size to actual load.

## Source

Pin function reference: [hotrodders.com ignition switch identification thread](https://www.hotrodders.com/threads/ignition-switch-identification.407881/)
