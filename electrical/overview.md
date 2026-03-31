# Electrical System Overview

## Design Philosophy

Relay-based system. The ignition switch and all dash switches carry only coil
trigger current. High-current loads run on short direct paths from battery
through relays. This eliminates voltage drop through dash switches and switch
contact wear.

## Power Distribution

Single heavy feed from battery positive to starter solenoid B+ lug (main
distribution point). Fuse box feeds from starter lug via 6 AWG wire, fused
at 60A ANL fuse at the battery. All relay 30 pins (always-hot inputs) feed
from battery or starter lug, fused individually at the load.

## Key Switch Wiring

Ignition switch: Standard Ignition US105. Two switched outputs used:

- **ACC (pink wire)** — triggers Relay 1 coil (pin 86)
- **IGN/RUN (purple wire)** — triggers Relay 2 coil (pin 86)

Key behavior:
- ACC position: Relay 1 energized only
- IGN/RUN position: Relay 1 and Relay 2 both energized
- Key off: both relays drop, all switched loads dead

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

- Main power (large red wire): battery + via starter lug, always hot
- Small red wire (ignition input): fed from Relay 2 pin 87 (IGN/RUN output)
- Ballast resistor: removed, not used with MSD
- Solenoid R terminal: leave empty

See [msd-6200/](msd-6200/) for full wiring details.

## Starter Circuit

GM-style solenoid mounted on starter.

- **B+ lug**: battery cable, alternator output, fuse box feed, MSD main power
- **S terminal**: start button wire only — nothing else on this lug
- **R terminal**: unused, leave empty

## Alternator

Powermaster 67293 (polished), CS130-style one-wire. Output wire runs to
starter solenoid B+ lug. No external voltage regulator required.

See [alternator/](alternator/) for belt sizing and installation notes.

## Wire Gauges

| Circuit | Gauge |
|---------|-------|
| Battery to starter lug | 2 AWG or larger |
| Alternator output | 4 AWG |
| Fuse box feed | 6 AWG |
| Relay 30/87 (high current loads) | 10 AWG minimum |
| Relay trigger/coil wiring | 18 AWG |
| MSD small red | 18 AWG |

## Grounds

Each major load gets a dedicated ground to chassis. No daisy-chained grounds.
Engine block grounded to chassis with minimum 2 AWG strap.
