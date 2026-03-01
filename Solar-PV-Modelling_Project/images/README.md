# Project Figures – Solar PV Modelling

This folder contains all figures related to the MATLAB/Simulink 
single-diode photovoltaic (PV) module modelling project.

The figures illustrate the model architecture, subsystem design, 
simulation results, and comparison with experimental data.

---

## Model Architecture

- Top-level Simulink PV module model
- Internal subsystem structure
- Temperature conversion block
- Photocurrent calculation block
- Reverse saturation current block
- Temperature-adjusted saturation current block
- Thermal voltage (NsAKT) block
- Output current computation block

These figures demonstrate the modular implementation of the 
single-diode PV model in Simulink.

---

## Simulation Results (STC – 25°C)

- I–V characteristics at 100, 200, 600, and 1000 W/m²
- P–V characteristics at 100, 200, 600, and 1000 W/m²
- Simulated I–V curves
- Simulated P–V curves

These plots show the expected nonlinear PV behaviour and 
maximum power point (MPP) variation with irradiance.

---

## Simulation vs Experimental Comparison

- I–V comparison at 1000 W/m²
- P–V comparison at 1000 W/m²
- I–V comparison at 600 W/m²
- P–V comparison at 600 W/m²
- I–V comparison at 200 W/m²
- P–V comparison at 200 W/m²
- I–V comparison at 100 W/m²
- P–V comparison at 100 W/m²

These comparisons validate the accuracy of the single-diode model.

---

## NOCT Analysis

- Simulated I–V curve at 800 W/m² and 46°C

This demonstrates model performance under Nominal Operating 
Cell Temperature (NOCT) conditions.

---

## Notes

- All plots were generated from MATLAB/Simulink simulation outputs.
- Experimental curves were digitized from manufacturer data for comparison.
- Minor deviations are attributed to bypass diode behaviour and 
  simplified thermal modelling in simulation.

