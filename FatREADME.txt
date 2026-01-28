# Satellite Fatigue Analysis – Enhanced Variable Amplitude Life Prediction

Advanced fatigue life estimation for simulated satellite structural components under realistic LEO mission loading.

This script performs **variable-amplitude fatigue analysis** using rainflow cycle counting, mean-stress correction (Walker or Gerber), notch effects, temperature derating, occasional high-load events, Monte-Carlo uncertainty quantification, and optional non-linear damage accumulation — all implemented with the excellent `fatpack` library.

## Features

- Realistic **7075-T73 aluminum** material properties
- Custom three-slope S-N curve (no infinite-life cutoff – conservative high-cycle behavior)
- Mean-stress correction: **Walker** (recommended) or Gerber
- Notch effects using **Kt** (mean) + **Kf** (amplitude)
- Temperature derating of fatigue strength (orbital thermal extremes)
- Occasional high-amplitude events (maneuvers, docking, etc.)
- Monte-Carlo simulation with noise → mean damage + standard deviation
- Life prediction in **orbits** and **calendar years** (LEO orbit rate)
- Optional **Corten-Dolan** non-linear damage rule
- Optional **signed von Mises** equivalent stress for multiaxial cases
- Block-loading sequence effect check (vs. full cycle-by-cycle Miner sum)
- Exports: rainflow matrix, range histogram (CSV)
- Diagnostic plots: stress history, range distribution, rainflow matrix heatmap

## Requirements

```text
Python 3.8+
numpy
matplotlib
fatpack     # pip install fatpack