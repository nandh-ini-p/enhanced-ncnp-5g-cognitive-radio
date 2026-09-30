# Project Overview

## Scope
This repository documents an academic project on an enhanced Non-Coherent Neyman-Pearson (NCNP) detector for 5G waveform detection in cognitive radio systems during disaster scenarios. Based on the available project materials, the work combines MATLAB-based simulation, energy detection, Wiener filtering, and a LabVIEW/USRP-2901 hardware path.

## Core problem
The project addresses the need for reliable spectrum sensing when communication infrastructure is damaged or congested during emergencies. The underlying objective is to detect usable spectrum under noise and interference while preserving a practical detection approach for emergency communication.

## Methodology described or proposed in the available documentation
- Signal acquisition and sensing in a target band
- Energy-based detection and threshold comparison
- NCNP hypothesis testing for noise-only vs signal-plus-noise decisions
- Filtering and noise conditioning, including Wiener filtering
- Evaluation through Pd, Pfa, and ROC-style analysis
- A proposed hardware implementation using USRP-2901 within a LabVIEW environment

## Evidence-based notes
The repository deliberately avoids unsupported claims. The checked-in materials confirm the following:
- The project is focused on cognitive radio and 5G waveform detection.
- MATLAB simulation is described for QAM signal generation and performance analysis.
- USRP-2901 and LabVIEW are part of the hardware implementation.
- Wiener filtering and ROC/Pd-Pfa analysis are part of the project methodology.

The following details remain unresolved in the checked-in repository and are marked as [TO BE CONFIRMED]:
- exact simulation parameters and SNR ranges
- specific sample rates and hardware settings
- quantitative results and plots
- team-member contribution breakdown
- final reference list and academic metadata

## Repository status
The repository currently contains project documentation and placeholder directories for implementation assets. No final MATLAB or LabVIEW source files, measured results, or finalized figures are present at this time.

## Intended structure
The project is organized around:
- `src/matlab/` for MATLAB simulation assets
- `src/labview/` for LabVIEW hardware workflow assets
- `results/` for measured outputs and summary statistics
- `figures/` for plots and visual analysis
- `docs/` for supporting project notes

## Summary
This project is best understood as a documentation-first academic repository that reflects the evidence in the available project materials. The technical direction is clear, but several implementation and validation details remain incomplete and are intentionally left as placeholders.
