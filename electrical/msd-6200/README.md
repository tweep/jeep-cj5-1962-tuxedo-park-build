# MSD 6200

Six-wire-capable box in this build: **points distributor** (no magnetic pickup). Full relay context: [overview.md](../overview.md); B+ routing: [fuse-box/b-plus-distribution.md](../fuse-box/b-plus-distribution.md).

## Main power (large wires)

| Connection | Routing |
|------------|---------|
| **Positive** | **70 A breaker OUT** → **10 AWG** → **10 A** inline fuse → **MSD large red** (see [b-plus-distribution.md](../fuse-box/b-plus-distribution.md)). Confirm amp rating with MSD’s chart for your wire length. |
| **Ground** | Chassis ground (same quality ground strategy as the rest of the ignition). |

## Not used — magnetic pickup

The **red / purple** pair for **magnetic pickup** is **not connected** — this engine uses a **points-style distributor**, not an MSD magnetic pickup.

## Small harness (four wires)

| Wire | Color | Connection |
|------|-------|------------|
| Trigger | **White** | To **tachometer** signal and to the **points distributor** (breaker points input). |
| Ignition switched | **Red** | **Ignition-switched** power (RUN)—keeps the engine running with the key in RUN; turns off when you switch ignition **off**. In the relay layout this is the **IGN/RUN** bus (e.g. Relay 2 pin 87 and related). |
| Ground | **Black** | Ground (MSD small-ground return). |
| Coil | **Orange** | To **Accel** (or compatible) **coil** primary—MSD controls energy to the coil on this wire. |

## Ballast resistor

**Removed.** The MSD box regulates delivery to the coil through the **orange** wire; an external ballast resistor is **not** used to drop voltage to the coil.

## Starter solenoid

**R terminal:** leave empty (no ballast/bypass path).

## Quick checklist

- [ ] Large **+**: **70 A breaker OUT** → **10 AWG** → **10 A** inline → MSD; large **ground** to chassis.
- [ ] Magnetic pickup wires **not** used (points ignition).
- [ ] **White** to tach + points distributor.
- [ ] **Red** on switched ignition / IGN bus.
- [ ] **Black** grounded.
- [ ] **Orange** to coil primary; no ballast resistor in series.
