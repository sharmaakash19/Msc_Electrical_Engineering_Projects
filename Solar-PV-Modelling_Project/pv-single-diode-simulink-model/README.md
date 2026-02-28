# Single-Diode Photovoltaic (PV) Module Modelling in MATLAB/Simulink

## Overview

This project implements a single-diode photovoltaic (PV) model of the 
Sun module SW 85 Poly R5A (85 W) using MATLAB/Simulink.

The objective is to simulate the I–V (Current–Voltage) and 
P–V (Power–Voltage) characteristics of the module under different 
irradiance and temperature conditions and compare them with 
experimental manufacturer data.

The model is based on the classical single-diode equivalent circuit 
and incorporates temperature and irradiance dependency.

---

## PV Module Specifications (STC)

Standard Test Conditions (STC):
- Irradiance: 1000 W/m²
- Temperature: 25°C
- Air Mass: 1.5

Electrical Parameters:

- Rated Maximum Power (Pmax): 85 W
- Open Circuit Voltage (Voc): 22 V
- Short Circuit Current (Isc): 5.2 A
- Voltage at MPP (Vmpp): 17.9 V
- Current at MPP (Impp): 4.77 A
- Number of Series Cells (Ns): 36
- Number of Parallel Strings (Np): 1

---

## Equivalent Circuit Model

The PV module is modelled using the single-diode equivalent circuit consisting of:

- Photocurrent source (Iph)
- Diode (Shockley equation)
- Series resistance (Rs)
- Shunt resistance (Rsh)

The output current is governed by the nonlinear equation:

I = Iph − Io [exp((V + I·Rs) / (n·Vt)) − 1] − (V + I·Rs)/Rsh

Where:
- Io = Reverse saturation current
- n = Diode ideality factor
- Vt = Thermal voltage
- V = Output voltage
- I = Output current

---

## Simulink Architecture

The complete Simulink model is structured into modular subsystems:

1. Celsius to Kelvin Conversion  
   Converts temperature input from °C to Kelvin.

2. Photocurrent Subsystem  
   Computes irradiance and temperature-dependent photocurrent.

3. Reverse Saturation Current  
   Calculates diode reverse saturation current.

4. Temperature-Adjusted Saturation Current  
   Adjusts Io for temperature variation.

5. Thermal Voltage (NsAKT) Block  
   Computes thermal voltage scaling factor.

6. Output Current Subsystem  
   Implements the nonlinear PV current equation.

This modular architecture allows easy adjustment of parameters 
for different environmental conditions.

---

## Simulation Conditions

The model was tested under multiple irradiance levels:

- 100 W/m²
- 200 W/m²
- 600 W/m²
- 1000 W/m²

Temperature was maintained at 25°C for standard analysis.

---

## Generated Outputs

The following outputs were obtained:

- I–V characteristics for all irradiance levels
- P–V characteristics for all irradiance levels
- Maximum Power Point (MPP) extraction
- Fill Factor (FF) calculation
- Comparison with experimental manufacturer curves

---

## NOCT Performance Simulation

The model was further tested under Nominal Operating Cell Temperature (NOCT):

- Irradiance: 800 W/m²
- Temperature: 46°C
- Air Mass: 1.5

Results were compared against manufacturer data to evaluate accuracy.

Observed deviations are primarily due to:
- Absence of bypass diode modelling
- Idealized assumptions in simulation
- Simplified thermal modelling

---

## Key Observations

- Short circuit current increases linearly with irradiance.
- Open circuit voltage varies logarithmically.
- MPP shifts with irradiance variation.
- Fill Factor deviation from experimental values remained within ±1%.
- Larger deviation observed under NOCT due to real-world bypass diode effects.

---

## Tools Used

- MATLAB
- Simulink
- Excel (for curve digitization and comparison)

---

## Conclusion

The developed single-diode model accurately reproduces 
the nonlinear behaviour of the PV module under varying 
irradiance and temperature conditions.

The simulation results closely match experimental data 
under STC conditions, validating the model for design 
and analysis purposes.

Future improvements may include:
- Explicit bypass diode modelling
- Enhanced thermal modelling
- MPPT algorithm integration
