# Switches, lights & relays

Dash switches, **headlight pull**, **column multifunction** stalk (turn signals, brake lights, indicators), and add-on **relays**. High-level relay strategy: [overview.md](../overview.md). Ignition column reference (unused in this build): [column-switch/](../column-switch/).

## Contents

| Doc | Description |
|-----|-------------|
| [diagrams.md](diagrams.md) | ACC bus, relay pin 30, key-independent loads (mermaid) |
| [column-multifunction-switch.md](column-multifunction-switch.md) | Haywire **3 7/8"** connector; **American Autowire 500428**; cable → signal → **my color**; photo |
| [headlight-switch/README.md](headlight-switch/README.md) | Headlight pull switch wire colors and annotations |

### Column turn-signal connector (Haywire)

The [column switch doc](column-multifunction-switch.md) uses the **Haywire & Co.** **GM OEM** connector: **3 7/8" turn signal**, **column side**, **male with terminals**—not a generic “9-terminal” switch label. **Brake (BW)** on black/white is **routed** to **green** or **yellow/black** by turn position; **turn** (**purple/black**) and **hazard** (**brown/black**) flasher feeds stay **separate** so they **do not interfere**.

**Eckler’s**, **Lectric Limited**, and other **GM restoration** suppliers use the **same color code** for **cross-reference** or **pigtail** sourcing. **American Autowire 500428** (1969+ GM column kit) includes **male + female** pairs for **3-7/8 in.** and **4-1/4 in.** connectors—see [column-multifunction-switch.md](column-multifunction-switch.md). General column wiring context: [Speedway Motors — Steering Column Wiring Guide](https://www.speedwaymotors.com/the-toolbox/steering-column-wiring-guide/28822).

## Switches (inventory)

Add one row per part as you install them.

| Function | Part / source | Mount | Notes |
|----------|---------------|-------|-------|
| | | | |

## Relays (inventory)

| Role | Part (e.g. ISO 5-pin) | Coil trigger | Load | Fuse | Notes |
|------|------------------------|--------------|------|------|-------|
| | | | | | |

## Images

**Pasting in the chat does not save files into this repo.** To attach photos:

1. Save the image on your machine (PNG or JPG is fine).
2. Copy it into **`switches-lights-relais/images/`** in this project (or use Finder drag-and-drop into the Cursor file tree).
3. Reference it in this file with Markdown (image description in brackets, path in parentheses pointing to `images/…`).

Use **short, lowercase filenames without spaces** so links stay reliable on GitHub and in editors.

| Photo | File (in `images/`) |
|-------|---------------------|
| | |

## Future

**Hydraulic brake-light switch** (line pressure) and wiring into the **Chevy/GMC column adapter** harness—schematic TBD.

## Related

- [fuse-box/](../fuse-box/) — panel, breaker, branch fuses  
- [ignition/](../ignition/) — US105 dash ignition  
