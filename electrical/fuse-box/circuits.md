# Electrical Circuits & Protection Map

Companion to [overview.md](../overview.md) (relay pinouts and logic) and [README.md](README.md) (fuse box feed). This document ties **overcurrent protection**, **wire size**, and **loads** together so you can verify or change one field without losing the whole picture.

## How power flows

Authoritative **B+ stud** diagrams (alternator **6 AWG** unfused, **2 AWG** battery, **70 A** breaker, **MSD** vs **Blue Sea**): **[b-plus-distribution.md](b-plus-distribution.md)**.

1. **Battery** positive **2 AWG** to **starter solenoid B+ stud**.
2. **Alternator** **6 AWG** unfused to the same **B+ stud**.
3. **B+** **6 AWG** to **70 A breaker IN**; **OUT** splits to **6 AWG** → **Blue Sea** and **10 AWG** → **10 A** fuse → **MSD large red**.
4. **Relays** (add-on) — each **pin 30** feed fused for that load only.

Always-hot relay feeds (headlights, light bar, etc.) must stay fused even when the key is off.

## Upstream protection (battery to B+ stack)

| Location | Device | Wire | Notes |
|----------|--------|------|--------|
| B+ stud → breaker → fuse box | **70 A DaierTek** | **6 AWG** from breaker **OUT** to Blue Sea | From B+ **IN** on **6 AWG** |
| Breaker OUT → MSD | **10 A** inline + **10 AWG** | Per [b-plus-distribution.md](b-plus-distribution.md) | Large red; chassis ground separate |
| Battery to B+ | Battery cable | 2 AWG+ | — |

Trip/opening the **70 A breaker** cuts **both** the **Blue Sea** and **MSD** feeds that leave the breaker **output**; **B+** can still be live from the **battery** (2 AWG) and **alternator** (6 AWG unfused). Label and isolate before work.

Fill in **actual** fuse values, breaker part number, and wire colors in the vehicle.

## Starter solenoid B+ stud (what lands here)

Typical stack (bottom to top or as your hardware dictates—**record order and torque**):

| Connection | Wire / device | Gauge (overview) |
|------------|---------------|------------------|
| Battery cable | From battery | 2 AWG or larger |
| Alternator output | Powermaster 67293 ~160 A | **6 AWG** unfused to B+ stud |
| Fuse box feed | **70 A breaker OUT** → Blue Sea | **6 AWG** |
| MSD main | **70 A breaker OUT** → **10 A** inline → large red | **10 AWG** (see [b-plus-distribution.md](b-plus-distribution.md)) |
| Other | — | — |

## Relay circuits (load side)

Pin numbering is **ISO relay**: 30 = switched power in, 87 = out to load, 85/86 = coil, 85 = ground.

### Coil circuits (low current)

Coil current is small (often under 200 mA per relay). Runs are typically **18 AWG**. Fuses on coil feeds are optional; many builds rely on the upstream branch fuse. If you add inline fuses for coil 86 feeds, use **1–3A** max.

| Relay | Coil 86 source | Ground 85 | Notes |
|-------|----------------|-------------|--------|
| 1 — ACC | US105 pink (ACC) | Chassis | Key ACC or RUN |
| 2 — IGN/RUN | US105 purple (IGN) | Chassis | Key RUN only for purple; see overview |
| 3 — Headlights | Dash headlight switch | Chassis | Key-independent trigger |
| 4 — LED bar | Dash switch (IGN-switched supply to switch) | Chassis | Logic per your dash |
| 5 — Rear aux | Dash switch | Chassis | — |

### Pin 30 feeds (high current) — fuse each branch

Each relay’s **pin 30** should come from battery/B+ through a **fuse sized to that load**, not to the sum of all relays.

| Relay | Load on 87 | Est. current @ 12.6 V | Suggested fuse (start here) | Min. wire (power) |
|-------|------------|------------------------|-------------------------------|-------------------|
| 1 — ACC | Radio, accessories | — | — | 10 AWG (overview min. for high-current relay paths) |
| 2 — IGN/RUN | MSD small red + other IGN loads | MSD sense: low; add other loads | — | 18 AWG MSD small red; heavier for any big IGN loads |
| 3 — Headlights | Headlamps | ~10–15 A typical (pair) | 15–20 A | 10–12 AWG |
| 4 — LED bar | ~400 W bar | **~33 A** | **35–40 A** | **8–10 AWG** (33 A continuous favors 8 AWG or short 10 AWG; verify temp rise) |
| 5 — Rear aux | Aux lamps | — | — | Match load |

Replace estimates with **measured** or **nameplate** values where possible.

## Fuse box branches (panel outputs)

Use this table for whatever **actually** leaves your fuse box—relay pin 30 feeds, dash circuits, USB chargers, etc.

| Slot / label | Fuse (A) | Wire gauge | Circuit / load | Key / always-on |
|--------------|----------|------------|----------------|-----------------|
| | | | | |
| | | | | |
| | | | | |

## Circuit summary by bus

| Bus | Key position | Typical loads |
|-----|--------------|----------------|
| ACC (Relay 1) | ACC, RUN | Radio, accessories on ACC relay |
| IGN (Relay 2) | RUN | MSD ignition input, other RUN-switched loads |
| Headlights (Relay 3) | Always-on trigger | Headlamps |
| LED bar (Relay 4) | Per dash wiring | High-draw LED |
| Rear aux (Relay 5) | Per dash wiring | Rear lighting |

## Grounds

Match [overview.md](../overview.md): dedicated chassis grounds per major load; engine block to chassis **≥ 2 AWG**.

## Revision log

| Date | Change |
|------|--------|
| 2026-04-04 | JY 21-circuit harness interim; planned Blue Sea 5032; 70 A breaker to panel; fused MSD main; diagram updated. |
