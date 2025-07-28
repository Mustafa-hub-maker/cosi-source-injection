# COSI Source Injector Simulations

This repository demonstrates how to simulate gamma-ray sources using the [COSI](https://cosi.lbl.gov) `SourceInjector` tool from the [`cosipy`](https://cosipy.readthedocs.io) framework. It includes:
- Simulations of the **Crab Nebula** using both Band and tabulated spectra
- Simulation of a **bright GRB** at an alternate sky location
- Comparative plots of simulated and injected spectra

---

### Files Overview

### Injected Data Files

| Filename                     | Description                                                        |
|------------------------------|--------------------------------------------------------------------|
| `Crab_model_injected.h5`     | Crab simulation using a Band function spectrum                     |
| `crab_piecewise_injected.h5` | Crab simulation using a tabulated `.dat` spectrum (`crab_spec.dat`) |
| `GRB_sim_bright_injected.h5` | Bright GRB injected at Galactic `l=120°, b=15°`                     |
| `model_injected.h5`          | (Possibly redundant/test file; can be removed or reused)           |

### Support Files

| Filename                                | Description                                              |
|-----------------------------------------|----------------------------------------------------------|
| `crab_spec.dat`                         | Tabular Crab spectrum used for piecewise injection       |
| `OPsSpectrum.dat`                       | Optional spectrum for additional injection experiments   |

### Code Scripts

| Script Filename               | Description                                      |
|-------------------------------|--------------------------------------------------|
| `Point_source_injector`       | Injects Crab source using Band & `.dat` spectra |
| `point_source_injector_new_data` | Injects a synthetic bright GRB source             |

---

## How It Works

### Point Source Injection
The process uses:
- An **instrument response file** (`*.h5`)
- A **source model** (spectrum + sky position)
- A **spacecraft orientation file** (`*.ori`)

It simulates how the COSI instrument would detect the source over a 3-month mission duration using the `SourceInjector`.

---

## Output Comparisons

The scripts generate plots comparing:
- Band vs. tabulated (piecewise) spectra for the Crab
- Injected GRB vs. simulated Crab
- Simulated (MEGAlib) vs. injected spectra

All projections are performed on energy (`Em`) using `histpy`.

---

