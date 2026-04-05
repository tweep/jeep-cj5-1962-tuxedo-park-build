# 1962 Jeep CJ5 Tuxedo Park – Build Log & Reference Manual

A living technical reference and work log for a 1962 Jeep CJ5 Tuxedo Park edition.

## Drivetrain

- **Engine:** Chevrolet 350 SBC, Holley 1850 four-barrel carburetor, Hedman headers
- **Transmission:** Borg Warner T18 (post-1978), four-speed manual
- **Transfer Case:** Scout Dana 20
- **Overdrive:** Warn 3326 (treat as an additional gear, clutch required to engage/disengage)
- **Front Axle:** Ford 9-inch from US Ford Bronco, 4.10 gears
- **Rear Axle:** Ford 9-inch from US Ford Bronco, 4.10 gears
- **Lockers:** Four-wheel hydraulic micro brake lockers

## Suspension & Steering

- **Shocks:** Rancho
- **Springs:** Rancho
- **Steering:** Saginaw power steering
- **Brakes:** Four-wheel disc (brand unknown)

## Hydraulics

- **Pedals:** [Wilwood 340-16833](https://www.summitracing.com/parts/WIL-340-16833) swing mount tandem pedal assembly
- **Brake Master:** [Tilton 74-1000U](https://www.summitracing.com/parts/TIL-74-1000U), 1" bore
- **Clutch Master:** [Wilwood 260-6764](https://www.summitracing.com/parts/wil-260-6764), 0.75" bore, high-volume, integral reservoir
- **Clutch Slave:** Original unit, 0.75" bore (blue). Likely replacement: Aisin CRT-012
  (13/16" bore, Toyota Land Cruiser 1974–1980) – same mounting pattern, slightly
  larger bore. Verify fit before ordering.

See [hydraulics/](hydraulics/) for full specs and plumbing notes.

## Electrical

- **Alternator:** [Powermaster Street 67293](https://www.summitracing.com/parts/PWM-67293#overview) (~160 A, GM 10SI/12SI family), 6 AWG unfused to starter B+; [electrical/fuse-box/b-plus-distribution.md](electrical/fuse-box/b-plus-distribution.md) for B+ diagram
- **Ignition Switch:** [Standard Ignition US105](https://www.oreillyauto.com/detail/c/standard-ignition/standard-ignition-starter-switch/std0/us105) starter switch

See [electrical/](electrical/) for full wiring documentation.

## Cooling

- **Fan:** [Derale 17318](https://www.summitracing.com/parts/DER-17318) rigid race fan, mechanical belt-driven

See [cooling/](cooling/) for specs and installation notes.

## Fuel

- Dual gas tanks

## Repository Structure
```
jeep-cj5-1962-tuxedo-park-build/
  README.md
  electrical/
    overview.md          # relay architecture, power rails, wire gauge map
    ignition/
    column-switch/
    switches-lights-relais/  # diagrams, column stalk, headlight, relay inventory
    alternator/
    msd-6200/
    fuse-box/
  drivetrain/
    engine/
    transmission/
    transfer-case/
    overdrive/
    axles/
  suspension/
  steering/
  brakes/
  hydraulics/
    brake/
    clutch/
  cooling/
  log/
    2026-03.md           # chronological work log by month
```

## Work Log

See [log/](log/) for chronological notes on work performed, parts sourced,
and decisions made.

## License

CC0 1.0 Universal – No rights reserved. See LICENSE for details.
