# Fuse Box & Distribution

## Role in this build

Power leaves the **starter solenoid B+ stud** to the fuse panel, the alternator,
and the MSD (see [circuits.md](circuits.md)). The fuse box is the **central place**
to split into **ATC branch fuses** for dash gear, lighting, and (via separate
relays) high-draw loads.

This build does **not** run high current through the ignition switch—relays carry
load current; the switch only energizes relay coils.

## Harness in use (JY Performance 21-circuit)

**Kit:** JY Performance Universal 21 Circuit Wiring Harness — extra-long leads,
**standard color** wiring, **17 ATC fuse** positions, labeled circuits. Picked up
used (~$70) as a practical alternative to sourcing colored wire alone: a CJ5 is
tight to rewire with all-black cable, and this kit matches hot-rod/GM conventions.

**Why it helps:** Pre-labeled branches, **Chevy column-style connectors** (useful
reference even with the dash US105 setup), and **MSD-friendly** runs (e.g. pink
ACC-related wiring) already routed and fused within the kit logic.

**Install note:** The bundle needs **depth** behind the panel—lots of circuits in
one place. Plan is to move to a **smaller, waterproof** panel (below) and keep
the color-coded tails that matter.

**Reference manual:** Wiring and circuit layout will follow **[Painless Performance manual 90555](https://painlessperformance.com/wp-content/uploads/2024/02/90555.pdf)** (PDF). It documents the same kind of universal 21-circuit harness conventions this kit follows, so wire colors, fuse assignments, and branch logic can be checked against that document during install.

## Planned: Blue Sea 5032 + relays

**Target panel:** [Blue Sea Systems 5032 ST Blade Fuse Block — Dual 12 with ground and cover, 100 A](https://www.amazon.com/dp/B00WM2MWQ4) (~$45). Two banks of 12 **ATO/ATC** positions, common bus, ground bus, and **cover** for moisture resistance—smaller footprint than the open universal box, easier to seal in a CJ.

**Relays:** Add **4–5 standalone automotive relays** (e.g. ISO 5-pin) for loads
such as the **LED light bar** and other switched high-current branches—coils from
dash/US105 as already documented in [overview.md](../overview.md).

## Upstream protection

**B+ stud → breaker → loads:** **DaierTek 70 A DC circuit breaker** fed from the **B+ stud** on **6 AWG**. From the breaker **output**: **6 AWG** to the **Blue Sea** fuse box, and **10 AWG** through a **10 A** inline fuse to the **MSD large red**—see **[b-plus-distribution.md](b-plus-distribution.md)** for mermaid diagrams.

**Alternator → B+:** **6 AWG**, **unfused**, to the same B+ stud (see [b-plus-distribution.md](b-plus-distribution.md)).

## Documents

| File | Contents |
|------|----------|
| [b-plus-distribution.md](b-plus-distribution.md) | **Mermaid:** B+ stud — alternator, battery, 70 A breaker → MSD (10 AWG + 10 A) & Blue Sea (6 AWG) |
| [circuits.md](circuits.md) | Protection map, B+ stack, relay fuse table, fuse box slot table, bus summary |

## Fuse box hardware (record yours)

| Field | Value |
|-------|--------|
| Current harness | JY Performance 21-circuit / 17 ATC (interim) |
| Planned panel | Blue Sea 5032 (dual 12 + cover) |
| Main feed protection | 70 A DaierTek breaker, B+ → fuse box |
| Mount location | |
| External relays | 4–5 (e.g. LED bar, other loads) |

## Design rules (this Jeep)

1. **One fuse per high-current branch** — especially each relay **pin 30** feed.
2. **Size the fuse to the wire and load** — fuse protects wire; wire must carry continuous load without overheating.
3. **70 A breaker** on the fuse box feed limits fault current for the whole panel run; **ATC branches** below that protect individual circuits.
4. **LED light bar (~33 A)** needs a **35–40 A** fuse and adequate **gauge** (see [circuits.md](circuits.md)); do not share that fuse with unrelated loads—typically via its **own relay**.

## Related

- Relay pinouts and US105 logic: [overview.md](../overview.md)
- MSD: [msd-6200/](../msd-6200/)
- Ignition switch: [ignition/](../ignition/)
