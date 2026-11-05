# Technical Notes — Baseline Microstrip Line

## Purpose

Establish a reference two-port microstrip transmission line model in CST Studio Suite for a subsequent ground-plane slot / defected ground structure (DGS) study.

## Model visible in screenshots

- 8–12 GHz simulated frequency range.
- Target/design parameter: `main_frequency = 10`.
- Two ports at opposite ends of the top signal strip.
- Ground plane appears continuous (no etched DGS in the submitted model).
- Model extent parameters: X = [−15, +15]; Y = [−12.5, +12.5].
- Z boundaries: 0, 0.035, 1.635, 1.670.
- Port parameters: `PortWidth = 15`, `PortHeight = 8`.
- Dimensions are in **CST model units**, presumed mm; confirm the unit setting. Confirm actual material assignments, layer mapping and strip width in the CST project.

## Main observations (from submitted screenshots)

| Quantity | Observation | Precision |
|---|---|---|
| S11 at 10.00399 GHz | −45.28933 dB | Read directly from marker |
| S11 at 8.495888 GHz | −36.04821 dB | Read directly from marker |
| S11 at 11.50613 GHz | −35.55890 dB | Read directly from marker |
| S11 minimum | ~−48 dB near 9.75 GHz | Estimated from graph |
| S21 at 10 GHz | ~−1.06 dB | Estimated from graph |
| S21 at 8 GHz | ~−0.85 dB | Estimated from graph |
| S21 at 12 GHz | ~−1.31 dB | Estimated from graph |

### Interpretation

A low S11 magnitude at 10 GHz indicates little input reflection in the simulated two-port setup. S21 close to −1 dB indicates some forward transmission loss. Low reflection alone does not imply lossless power transmission; conductor and dielectric losses and other effects may contribute. Do not infer a validated experimental insertion loss from these simulated plots.

## Recommended next exports

1. Open the included `CST_Project/XBand_Microstrip.cst` in CST to verify materials, port setup, and reproducibility.
2. Export S11 and S21 numerical data for the exact simulated frequency points.
3. Record the dielectric properties (relative permittivity and loss tangent), copper properties, trace width, and CST simulation/port settings.
4. Optionally perform and document mesh refinement/convergence; do not label the supplied port-side view as a mesh image.
5. In future DGS runs, retain an unmodified baseline and compare all variants with consistent plotting and boundary/port settings.
