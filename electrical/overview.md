# Electrical System Overview

See [README.md](README.md) for a topic index and quick links.

## Design Philosophy

Relay-based system. The ignition switch and all dash switches carry only coil
trigger current. High-current loads run on short direct paths from battery
through relays. This eliminates voltage drop through dash switches and switch
contact wear.

## Power Distribution

**Starter B+ stud** is the junction: **2 AWG** to battery, **6 AWG** unfused from alternator (~160 A), **6 AWG** to **70 A** breaker **IN**; breaker **OUT** → **6 AWG** to **Blue Sea** and **10 AWG** + **10 A** to **MSD** large red—see **[fuse-box/b-plus-distribution.md](fuse-box/b-plus-distribution.md)**. All relay **30** pins (always-hot inputs) are fused per branch at the load.

Relay tables and branch details: [fuse-box/circuits.md](fuse-box/circuits.md).

## Key Switch Wiring

Ignition switch: Standard Ignition US105. Two switched outputs used:

- **ACC (pink wire)** — triggers Relay 1 coil (pin 86)
- **IGN/RUN (purple wire)** — triggers Relay 2 coil (pin 86)

Key behavior:
- ACC position: Relay 1 energized only
- IGN/RUN position: Relay 1 and Relay 2 both energized
- Key off: both relays drop, all switched loads dead

The GM **column** ignition switch is not used in this build (connector disconnected). Reference only: [column-switch/](column-switch/).

### US105 → relay summary

| Key position | ACC (pink) | IGN/RUN (purple) | Relay 1 (ACC bus) | Relay 2 (IGN bus) |
|--------------|------------|------------------|-------------------|-------------------|
| OFF | open | open | off | off |
| ACC | closed | open | on | off |
| RUN | closed | closed | on | on |

Confirm switch terminal behavior with a meter on your harness; wire colors follow common US105 practice.

## Relay Layout

All relays are standard ISO 5-pin automotive relays with pre-made pigtail
harnesses. Pin colors on installed harnesses: 30=red, 85=black, 86=white,
87=yellow.

### Relay 1 — ACC

| Pin | Wire | Connection |
|-----|------|------------|
| 30  | RED  | Battery + (always hot, fused) |
| 85  | BLK  | Chassis ground |
| 86  | WHT  | ACC signal from ignition switch (pink wire) |
| 87  | YEL  | ACC bus → radio, accessories |

### Relay 2 — IGN/RUN

| Pin | Wire | Connection |
|-----|------|------------|
| 30  | RED  | Battery + (always hot, fused) |
| 85  | BLK  | Chassis ground |
| 86  | WHT  | IGN/RUN signal from ignition switch (purple wire) |
| 87  | YEL  | MSD 6200 small red wire (direct, no switch) + IGN loads |

### Relay 3 — Headlights

| Pin | Wire | Connection |
|-----|------|------------|
| 30  | RED  | Battery + (always hot, fused) |
| 85  | BLK  | Chassis ground |
| 86  | WHT  | Headlight dash switch (always available, not key-dependent) |
| 87  | YEL  | Headlights |

### Relay 4 — LED Light Bar

| Pin | Wire | Connection |
|-----|------|------------|
| 30  | RED  | Battery + (always hot, fused) |
| 85  | BLK  | Chassis ground |
| 86  | WHT  | LED bar dash switch, enabled by IGN/RUN supply |
| 87  | YEL  | LED light bar (400W, 33A) |

### Relay 5 — Auxiliary Rear Lights

| Pin | Wire | Connection |
|-----|------|------------|
| 30  | RED  | Battery + (always hot, fused) |
| 85  | BLK  | Chassis ground |
| 86  | WHT  | Rear aux light dash switch |
| 87  | YEL  | Auxiliary rear lights |

## MSD 6200 Integration

- **Main:** fused **B+** (feeder tied to the **70 A** breaker path) and chassis **ground**
- **Magnetic pickup (red/purple):** not used — **points** distributor
- **Small harness:** white (tach + points), red (IGN switched), black (ground), orange (coil); **no ballast resistor** — MSD drives the coil via orange
- **Starter R terminal:** empty

See [msd-6200/](msd-6200/) for wire-by-wire details.

## Starter Circuit

GM-style solenoid mounted on starter.

- **B+ lug**: battery cable, alternator output, fuse box feed, MSD main power
- **S terminal**: start button wire only — nothing else on this lug
- **R terminal**: unused, leave empty

## Alternator

[Powermaster Street 67293](https://www.summitracing.com/parts/PWM-67293#overview) (~**160 A**), GM **10SI/10DN/12SI** case. **6 AWG** unfused to starter **B+**; **B+** → **70 A** breaker → [Blue Sea + MSD](fuse-box/b-plus-distribution.md). **45" V-belt** (smaller alternator pulley OD). Details: [alternator/](alternator/).

## Wire Gauges

| Circuit | Gauge |
|---------|-------|
| Battery to starter lug | 2 AWG or larger |
| Alternator output | 6 AWG (to starter B+ lug) |
| Fuse box feed | 6 AWG |
| Relay 30/87 (high current loads) | 10 AWG minimum |
| Relay trigger/coil wiring | 18 AWG |
| MSD small harness (white, red, black, orange) | Per MSD (often 18 AWG) |

## Grounds

Each major load gets a dedicated ground to chassis. No daisy-chained grounds.
Engine block grounded to chassis with minimum 2 AWG strap.
