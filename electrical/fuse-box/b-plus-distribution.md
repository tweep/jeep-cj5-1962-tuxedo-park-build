# Starter B+ distribution (alternator, breaker, MSD, fuse box)

The **starter solenoid B+ stud** is the central junction. This matches the as-built plan below; adjust if your stack order differs.

**Safety:** The **alternator** feed is **unfused** to B+ (normal). With the engine running, the alternator can still energize B+ after the battery is disconnected—treat the stud as live. Tripping the **70 A breaker** removes power to the **MSD** and **Blue Sea** branches that run **from that breaker’s output**, but **B+** can still be hot from the alternator and battery until those are isolated.

---

## Diagram 1 — Full path (authoritative)

```mermaid
flowchart TB
  ALT[Alternator ~160 A]
  BPLUS[B+ starter solenoid stud]
  BAT[Battery +]
  BRK[70 A circuit breaker]
  F10[10 A inline fuse]
  MSD[MSD large red in]
  FB[Blue Sea fuse box]

  ALT -->|6 AWG unfused| BPLUS
  BAT -->|2 AWG| BPLUS
  BPLUS -->|6 AWG to IN| BRK
  BRK -->|10 AWG OUT| F10
  F10 --> MSD
  BRK -->|6 AWG OUT| FB
```

| Path | Wire | Protection / destination |
|------|------|-------------------------|
| Alternator → B+ | **6 AWG** | **No fuse** (single cable to stud) |
| B+ → Battery + | **2 AWG** | Main battery connection |
| B+ → breaker **IN** | **6 AWG** | Feeds breaker |
| Breaker **OUT** → MSD | **10 AWG** → **10 A** inline fuse → MSD **large red** | Branch fuse sized for MSD feed |
| Breaker **OUT** → panel | **6 AWG** → **Blue Sea** fuse block | ATC branches from there |

**MSD ground:** Large black to chassis (not shown)—see [msd-6200/README.md](../msd-6200/README.md).

---

## Diagram 2 — Breaker outputs only (MSD vs fuse box)

Use this when talking about “what leaves the 70 A breaker.”

```mermaid
flowchart LR
  BRK[70 A breaker OUT]
  subgraph MSDbranch [MSD branch]
    W10[10 AWG]
    F10[10 A inline]
    MSD[MSD large red]
  end
  subgraph Panelbranch [Fuse box branch]
    W6[6 AWG]
    FB[Blue Sea]
  end
  BRK --> W10 --> F10 --> MSD
  BRK --> W6 --> FB
```

---

## Related

- [circuits.md](circuits.md) — broader protection map and relay tables  
- [README.md](README.md) — harness, Blue Sea 5032, breaker choice  
- [../alternator/README.md](../alternator/README.md) — alternator part and belt  
