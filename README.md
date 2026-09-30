# Enhanced NCNP Detector for 5G Waveform Using Cognitive Radio During Disasters

## 1. Project Title
Enhanced NCNP Detector for 5G Waveform Using Cognitive Radio During Disasters

## 2. Short technical description
This project studies spectrum sensing for emergency communication using an enhanced Non-Coherent Neyman-Pearson (NCNP) detector in a 5G cognitive radio context. Based on the available project documentation, the work combines MATLAB-based simulation, energy-based detection, Wiener filtering, and a USRP-2901/LabVIEW implementation for signal acquisition and performance evaluation.

## 3. Problem Statement
During natural disasters, conventional communication infrastructure may be disrupted or overloaded. In such conditions, reliable spectrum sensing is needed to identify available channels and support resilient emergency communication. The project addresses this by evaluating detector-based sensing in noisy and interference-prone conditions relevant to disaster scenarios.

## 4. Motivation
Cognitive radio systems can detect idle spectrum and support dynamic access when communication resources are constrained. In disaster response scenarios, this is relevant for maintaining coordination, supporting emergency services, and improving the efficiency of limited wireless resources.

## 5. Objectives
- Investigate NCNP-based spectrum sensing for 5G waveform detection.
- Analyze probability of detection (Pd) and probability of false alarm (Pfa) behavior under varying SNR conditions.
- Evaluate the influence of filtering and noise conditioning on detection performance.
- Examine a hardware-oriented implementation using USRP-2901 and LabVIEW.
- Document the project in a research-oriented repository suitable for academic portfolio review.

## 6. System / Methodology Overview
The project employs a cognitive radio workflow based on signal observation, noise evaluation, decision making, and performance assessment. The available documentation identifies the following stages:
1. Signal acquisition and spectrum sensing.
2. Energy-based detection and threshold comparison.
3. Filtering or noise conditioning, including Wiener filtering.
4. Probability-of-detection and false-alarm evaluation.
5. ROC-based comparison and discussion of detection performance.

## 7. Cognitive Radio Workflow
- Acquire the received signal in the target band.
- Estimate or compare the signal against the noise floor.
- Apply detection logic based on the NCNP decision rule.
- Decide whether the band is available or occupied.
- Record detection performance metrics such as Pd and Pfa.

## 8. Proposed Detection Approach
The available documentation describes a non-coherent Neyman-Pearson detector for signal detection under uncertain phase and signal conditions. The detector compares the received signal against a null hypothesis of noise-only conditions and an alternative hypothesis of signal plus noise.

The earlier project description sketches an energy-based statistic and thresholding logic:

```text
Λ(x) = Σ |x[n]|²
If Λ(x) > λ(Pfa), decide H1
Else, decide H0
```

The exact NCNP test statistic and threshold derivation remain [TO BE CONFIRMED] from the implementation; this expression should not be treated as a verified mathematical specification.

## 9. MATLAB Simulation
The project documentation indicates MATLAB-based simulation for 5G waveform and detection analysis. The available evidence includes the following tasks:
- QAM-based signal generation
- energy detection
- Pd/Pfa analysis versus SNR
- noise and filter comparison
- ROC curve generation
- Wiener filtering

Specific simulation parameters such as FFT size, sample rate, duration, SNR range, and number of Monte Carlo trials are not yet documented in the repository and are therefore marked as [TO BE CONFIRMED].

## 10. Hardware / Software Implementation
### 10.1 USRP-2901
The project documentation describes a USRP-2901-based hardware implementation for software-defined radio experimentation, with signal acquisition and receiver-side work in a LabVIEW environment. The repository does not include hardware configuration files or measurement records.

### 10.2 LabVIEW
The available documentation identifies LabVIEW as the implementation environment for USRP control, real-time signal monitoring, and hardware-based receiver design.

### 10.3 MATLAB
MATLAB is used for simulation, signal generation, detection analysis, and evaluation of filtering effects.

Specific system settings such as exact USRP frequency range, IQ rate, gain, and ADC/DAC parameters are not yet fully documented in the checked-in repository and are marked as [TO BE CONFIRMED].

## 11. Results
The repository currently does not contain numerical results, plots, or quantitative summary tables. The project documentation describes MATLAB simulation and LabVIEW/USRP implementation as project components, and lists Pd/Pfa analysis, ROC comparisons, and Wiener filtering as evaluation work. The status and measurements for these activities are not independently documented in the repository. Results should therefore be treated as [RESULTS TO BE ADDED].

## 12. System Architecture / Block Diagram
```text
5G signal / spectrum band
          |
          v
    Signal acquisition
          |
          v
    Noise / filtering stage
    (Wiener filtering, noise conditioning)
          |
          v
   NCNP detector / energy decision
          |
          +---------------------------+
          |                           |
          v                           v
      H0: noise only            H1: signal + noise
          |
          v
   Pd, Pfa, ROC, and detection metrics
```

## 13. Technologies Used
- MATLAB
- LabVIEW
- USRP-2901
- Cognitive radio concept and spectrum sensing
- QAM-based waveform generation
- Energy detection
- Wiener filtering
- ROC and Pd/Pfa analysis
- Git and GitHub for repository management

## 14. Project Contributions
This project was developed as part of a team project. Individual team member contributions are not fully documented in the available repository materials, so the repository intentionally avoids assigning individual component ownership beyond the collective project work.

## 15. Limitations
- Quantitative results and final plots are not yet included in the repository.
- Exact waveform parameters and simulation settings remain [TO BE CONFIRMED].
- Exact USRP frequency range, sample rate, and hardware configuration remain [TO BE CONFIRMED].
- The repository does not yet contain final source code, measured data files, or formal validation records.
- The project documentation suggests analysis in noisy and disaster-relevant environments, but the precise operational conditions are not fully specified in the checked-in files.

## 16. Future Work
- Finalize and document quantitative simulation results.
- Add measured data and performance plots for Pd/Pfa and ROC comparisons.
- Document exact MATLAB and LabVIEW implementation parameters.
- Validate the system under additional noise, filtering, and channel scenarios.
- Extend the project documentation with a formal bibliography and test configuration notes.

## 17. References
The project documentation describes or proposes work in the following areas:
- 5G communication and cognitive radio
- NCNP-based spectrum sensing
- energy detection
- QAM waveform generation
- USRP-2901 hardware testing
- Wiener filtering and noise suppression
- ROC analysis and detection metrics

Formal citations for each topic are not yet included in the repository and should be added as [TO BE CONFIRMED].

## 18. Disclaimer / Academic Note
This repository is intended as a research-oriented academic portfolio artifact for an Electronics and Communication Engineering project. It is based only on the available project documentation and does not claim unsupported numerical or performance results. Where details are missing, they are marked as [TO BE CONFIRMED] rather than inferred.

## 19. Repository Structure
```text
enhanced-ncnp-5g-cognitive-radio/
├── README.md
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE                         # License selection remains unconfirmed
├── SECURITY.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── config.yml
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/
│   └── project-overview.md
├── src/
│   ├── matlab/
│   │   └── README.md
│   └── labview/
│       └── README.md
├── results/
│   └── README.md
└── figures/
    └── README.md
```

The current repository state includes documentation placeholders for MATLAB/LabVIEW work, results, and figures; implementation files, measured results, and figure assets are not yet present.

## 20. Current Status
This repository is best understood as a documentation and project-structure scaffold for an academic research project in progress. The available evidence supports the core technical direction, but the final implementation and quantitative results remain to be added.

## 21. Verification Notes
The project facts included here are based on the project documentation present in the repository. Where the repository does not include enough evidence, the text intentionally uses [TO BE CONFIRMED] instead of making assumptions.
