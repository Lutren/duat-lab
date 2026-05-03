# Psi Falsifier Lab

This document defines a safe public direction for speculative Psi-style models.
It does not claim that Psi is true.

## Model Position

Newton is treated as a local compression. Einstein is treated as a deeper
geometric model. A Psi-style toy model is only useful if it can:

- reproduce Newton in low-speed, weak-field regimes;
- reproduce relativistic observations where required;
- fail visibly when it cannot match an observable;
- make distinct predictions that can be tested.

## Variables

| symbol | public meaning |
|---|---|
| `Psi` | observational update field in a toy model |
| `L` | light/electromagnetic observation channel |
| `G` | gravitational observation channel |
| `F` | interaction/force channel |
| `O` | observer or measurement system |
| `R` | informational residue |
| `S` | observer/system saturation |
| `epsilon` | observational distortion |
| `Sigma` | observational signature |

## Required Observables

A public model must produce numbers for at least one observable:

- orbital trajectory;
- light deflection;
- time delay;
- frequency shift;
- energy estimate;
- measurement error.

## Required Tests

```text
duat_physics/
  models/
    newtonian.py
    relativistic.py
    psi_field.py
  tests/
    orbital_motion.json
    mercury_precession.json
    light_deflection.json
    gps_time_dilation.json
  falsifier.py
  observables.py
  report.py
```

## Allowed Output

```text
Psi reproduces this Newtonian fixture.
Psi fails this relativistic fixture.
Psi requires a different observable before promotion.
```

## Prohibited Output

```text
Psi is proven.
Newton is false.
Einstein is replaced.
Consciousness is proven.
```
