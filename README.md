# Enhanced NCNP Detector for 5G Waveform Using Cognitive Radio During Disasters

## 1. Project Title
**Enhanced Non-Coherent Neyman-Pearson (NCNP) Detector for 5G Spectrum Sensing Using Cognitive Radio in Emergency Communication Scenarios**

---

## 2. Technical Description
This project presents an enhanced implementation of a Non-Coherent Neyman-Pearson detector for spectrum sensing in 5G cognitive radio systems. The detector is optimized for emergency and disaster communication scenarios where rapid, reliable spectrum availability assessment is critical. The implementation combines MATLAB-based simulation and LabVIEW hardware integration using USRP-2901 software-defined radio (SDR) hardware.

---

## 3. Problem Statement
In disaster scenarios, emergency communication systems must rapidly identify available spectrum for first-responder coordination and public safety communications. Traditional spectrum sensing methods may fail under:
- Severe noise and fading conditions
- Time-constrained decision requirements
- Variable channel characteristics
- Limited computational resources in field conditions

The challenge is to develop a robust spectrum detection algorithm that maintains high probability of detection (Pd) while minimizing false alarms (Pfa) across a wide range of signal-to-noise ratios (SNR), particularly in low-SNR emergency scenarios.

---

## 4. Motivation
Cognitive radio technology enables dynamic spectrum access by intelligently identifying underutilized spectrum bands. During disasters, when conventional communication infrastructure may be damaged or overwhelmed, cognitive radio systems can opportunistically utilize vacant spectrum to maintain emergency communications. An enhanced NCNP detector provides:
- **Robustness**: Minimal a priori knowledge of signal characteristics required
- **Reliability**: Statistically optimal detection under unknown signal parameters
- **Adaptability**: Effective performance across varying SNR conditions

---

## 5. Objectives
- Design and implement an enhanced Non-Coherent Neyman-Pearson detector for 5G waveform detection
- Analyze detection performance (Pd/Pfa) characteristics across variable SNR conditions
- Evaluate the impact of filtering and noise conditioning on detection reliability
- Develop hardware implementation using USRP-2901 and LabVIEW
- Validate performance through simulation and practical measurement
- Document results suitable for academic and professional portfolio evaluation

---

## 6. System/Methodology Overview

### 6.1 Cognitive Radio Workflow
The cognitive radio system operates in the following cycle:
1. **Spectrum Sensing**: Monitor available spectrum bands for primary user signals
2. **Decision Making**: Determine spectrum availability using NCNP detection algorithm
3. **Channel Assessment**: Analyze noise floor and SNR conditions
4. **Adaptation**: Adjust detection thresholds or switch to alternative bands if necessary
5. **Communication**: Establish or maintain secondary user transmission on available spectrum

---

## 7. Cognitive Radio Workflow (Detailed)

### 7.1 Spectrum Sensing Module
- Captures received signals from target frequency band
- Conducts energy-based preliminary assessment
- Logs signal statistics (power, spectral characteristics)

### 7.2 NCNP Detection Engine
- Computes test statistic from received signal samples
- Applies adaptive threshold based on target false alarm rate
- Outputs binary detection decision
- Tracks performance metrics (Pd, Pfa, SNR)

### 7.3 Feedback and Learning
- Records detection decisions and actual outcomes
- Updates noise floor estimates
- Adjusts threshold for improved reliability in changing conditions

---

## 8. Proposed Detection Approach

### 8.1 Non-Coherent Neyman-Pearson Detector
The Non-Coherent Neyman-Pearson detector provides optimal detection under the following hypotheses:

**H₀ (Null)**: Noise only  
**H₁ (Alternative)**: Signal + Noise

The detector maximizes probability of detection for a fixed false alarm rate without requiring:
- Phase synchronization with the received signal
- Exact knowledge of signal amplitude
- Prior distribution of signal parameters

### 8.2 Enhanced Implementation
Enhancements to the base NCNP detector include:
- Adaptive threshold adjustment based on estimated noise characteristics
- Filtering strategies (Wiener filtering) for noise suppression
- Multi-sample hypothesis testing for improved reliability
- SNR-aware parameter tuning

### 8.3 Test Statistic Computation
[TO BE CONFIRMED: Detailed mathematical formulation from source code]

The detector computes:
```
Λ(x) = Σ|x[n]|² (energy detector variant)
```
Decision rule:
```
If Λ(x) > λ(Pfa), decide H₁ (Signal present)
Else, decide H₀ (Noise only)
```

where λ(Pfa) is the threshold derived from target false alarm rate.

---

## 9. MATLAB Simulation

### 9.1 Signal Generation
- **Modulation**: QAM (Quadrature Amplitude Modulation)
- **Subcarrier Structure**: [TO BE CONFIRMED: number of subcarriers, FFT size, subcarrier spacing]
- **Sample Rate**: [TO BE CONFIRMED]
- **Duration**: [TO BE CONFIRMED: simulation time window]

### 9.2 Energy Detection Analysis
The energy detector computes the received signal power:
```
E = (1/N) Σ|r[n]|²
```
where r[n] is the received signal sample and N is the observation window.

Performance is evaluated under:
- Varying SNR levels
- Different noise types (AWGN, filtered noise)
- Multiple sample observation windows

### 9.3 Probability of Detection (Pd) vs Probability of False Alarm (Pfa) Analysis
Simulation sweeps across SNR range to generate:
- Detection performance curves showing Pd as function of SNR
- False alarm rate variation with threshold selection
- Optimal threshold determination for target Pfa

### 9.4 SNR Analysis
- Simulated SNR range: [TO BE CONFIRMED: minimum to maximum dB values]
- Swept in [TO BE CONFIRMED: dB step size] increments
- For each SNR, [TO BE CONFIRMED: number] Monte Carlo trials executed

### 9.5 Filtering and Noise Comparison
- **Wiener Filter**: Linear optimal filter minimizing mean-squared error
  - Computed from estimated signal and noise autocorrelation
  - Applied to suppress noise while preserving signal features
- **Noise Conditioning Approaches**: 
  - [TO BE CONFIRMED: specific filtering strategies and their parameters]
- **Comparative Analysis**: Detection performance with/without filtering

### 9.6 ROC Curve Analysis
Receiver Operating Characteristic (ROC) curves plot:
- **X-axis**: Probability of False Alarm (Pfa)
- **Y-axis**: Probability of Detection (Pd)

Generated for:
- Different SNR levels
- Multiple filtering configurations
- Comparison of detector variants

### 9.7 Wiener Filtering
The Wiener filter provides optimal linear filtering under MSE criterion:

```
H_w(f) = S_s(f) / (S_s(f) + S_n(f))
```

where:
- S_s(f) = signal power spectral density
- S_n(f) = noise power spectral density

Implementation:
- Estimated from received signal statistics
- Applied in frequency or time domain
- Performance impact on Pd/Pfa documented

---

## 10. Hardware/Software Implementation

### 10.1 USRP-2901 Software-Defined Radio
- **Platform**: Universal Software Radio Peripheral (USRP) N200 series variant
- **RF Front-End**: Configurable transmit/receive chains
- **Frequency Range**: [TO BE CONFIRMED: tunable band from repository/documentation]
- **Sampling Rate**: [TO BE CONFIRMED]
- **ADC Resolution**: [TO BE CONFIRMED]

### 10.2 LabVIEW Implementation
- **Graphical programming environment** for real-time signal processing
- **USRP Control**: LabVIEW USRP driver integration
- **Real-time Detector**: Implementation of NCNP detection algorithm
- **Data Logging**: Records received samples, decisions, and performance metrics
- **UI Components**: 
  - Threshold adjustment controls
  - Real-time detection status indicator
  - Performance metric display

### 10.3 MATLAB
- **Simulation and Analysis**: Algorithm development and validation
- **Signal Generation**: QAM modulation, noise injection
- **Performance Evaluation**: Pd/Pfa computation, ROC curve generation
- **Filter Design**: Wiener filter coefficient computation
- **Visualization**: Plotting detection curves and comparative analysis

---

## 11. Results

### 11.1 Simulation Results
[RESULTS TO BE ADDED: Experimental data, performance curves, and quantitative measurements]

Planned results sections:
- Detection probability vs SNR curves
- ROC curves for multiple configurations
- Comparison: filtered vs unfiltered detection
- Wiener filter impact on detection performance
- False alarm rate analysis

### 11.2 Hardware Implementation Results
[RESULTS TO BE ADDED: USRP-based measurements and real-world validation]

Planned results sections:
- Real-time detection performance
- Spectrum sensing in practical channel conditions
- Comparison: simulation vs hardware measurements
- Performance in noise and fading scenarios

### 11.3 Summary Metrics
[TO BE CONFIRMED: Include only measurements actually obtained]
- Maximum Pd achieved at target SNR
- False alarm rate at optimal threshold
- Detection performance improvement with filtering
- Computational latency for real-time implementation

---

## 12. System Architecture / Block Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                    5G SPECTRUM BAND                         │
└─────────────────────────────────────────────────────────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │  USRP-2901   │
                    │  (RF + ADC)  │
                    └──────────────┘
                           │
                           ▼
        ┌──────────────────────────────────────┐
        │     SIGNAL CONDITIONING              │
        │  ┌────────────────────────────────┐  │
        │  │  Optional: Wiener Filtering    │  │
        │  └────────────────────────────────┘  │
        └──────────────────────────────────────┘
                           │
                           ▼
        ┌──────────────────────────────────────┐
        │   NCNP DETECTOR ENGINE               │
        │  ┌────────────────────────────────┐  │
        │  │ Energy Calculation             │  │
        │  ├────────────────────────────────┤  │
        │  │ Threshold Comparison           │  │
        │  ├────────────────────────────────┤  │
        │  │ Binary Decision Output         │  │
        │  └────────────────────────────────┘  │
        └──────────────────────────────────────┘
                           │
         ┌─────────────────┴─────────────────┐
         │                                   │
         ▼                                   ▼
    ┌─────────────┐               ┌──────────────────┐
    │ Detection:  │               │  Monitoring &    │
    │ H₀ or H₁    │               │  Performance     │
    └─────────────┘               │  Metrics (Pd,Pfa)│
                                  └──────────────────┘

┌──────────────────────────────────────────────────────────────┐
│  IMPLEMENTATION PLATFORMS                                    │
│  ┌─────────────┐  ┌──────────────┐  ┌──────────────────┐   │
│  │   MATLAB    │  │   LabVIEW    │  │  Real-Time OS    │   │
│  │ Simulation  │  │   Control &  │  │  (LabVIEW RT)    │   │
│  │ Analysis    │  │   UI         │  │  [TO BE          │   │
│  │             │  │              │  │   CONFIRMED]     │   │
│  └─────────────┘  └──────────────┘  └──────────────────┘   │
└──────────────────────────────────────────────────────────────┘
```

---

## 13. Technologies Used

| Category | Technology | Purpose |
|----------|-----------|---------|
| **Signal Processing** | MATLAB | Simulation, algorithm development, analysis |
| **RF Hardware** | USRP-2901 | Software-defined radio for spectrum sensing |
| **Real-Time Control** | LabVIEW | USRP interface, real-time detection, data logging |
| **Modulation** | QAM | 5G waveform simulation |
| **Detection** | Energy Detection, Neyman-Pearson Test | Binary hypothesis testing |
| **Filtering** | Wiener Filter | Noise suppression |
| **Analysis** | ROC Curves, Pd/Pfa Analysis | Performance evaluation |
| **Version Control** | Git/GitHub | Source code management |

---

## 14. Project Contributions

This was a **team project** in [TO BE CONFIRMED: course code and name].

**Developed as part of a team project.**

[Team member contributions to specific components are to be documented in separate documentation or acknowledged directly by the team. This repository documents the collective technical work and system integration.]

---

## 15. Limitations

### 15.1 Simulation Assumptions
- [TO BE CONFIRMED: AWGN channel model assumed]
- [TO BE CONFIRMED: Signal parameters and modulation index]
- Monte Carlo simulation with finite sample count (potential statistical variance)
- Ideal RF front-end characteristics in simulation

### 15.2 Hardware Implementation
- [TO BE CONFIRMED: Specific USRP frequency band limitations]
- [TO BE CONFIRMED: ADC/DAC resolution constraints]
- Real-world channel effects (fading, multipath) not fully characterized
- Computational latency [TO BE CONFIRMED] may affect decision timing

### 15.3 Detector Limitations
- Non-coherent detector optimal under unknown signal characteristics but may underperform if signal parameters are known
- Performance dependent on accurate noise floor estimation
- Threshold selection critical; suboptimal choice reduces Pd or increases Pfa
- [TO BE CONFIRMED: Other algorithm-specific constraints]

### 15.4 Scope Limitations
- Single primary user signal scenario (no multiple concurrent signals analyzed)
- [TO BE CONFIRMED: Specific frequency bands tested]
- [TO BE CONFIRMED: Duration and extent of field validation]

---

## 16. Future Work

1. **Extended Channel Models**: Incorporate Rayleigh/Rician fading, multipath propagation, and time-varying channels
2. **Cooperative Sensing**: Extend to multi-node cognitive radio networks for improved detection reliability
3. **Machine Learning Enhancement**: Investigate neural network-based threshold adaptation for improved Pd/Pfa tradeoff
4. **Real-Time Optimization**: Reduce computational latency for faster spectrum sensing decisions
5. **Wider Frequency Coverage**: Test and validate across multiple frequency bands (Sub-6 GHz, mmWave)
6. **Field Trials**: Conduct large-scale emergency scenario simulations
7. **Cross-Platform Implementation**: Port to alternative SDR platforms (USRP X-series, HackRF, BladeRF)
8. **Comparative Analysis**: Benchmark against other spectrum sensing techniques (cyclostationary detection, feature detection)
9. **Energy Efficiency**: Optimize power consumption for battery-operated emergency communication devices
10. **Standards Compliance**: Validate against IEEE 802.22 and 3GPP spectrum sensing specifications

---

## 17. References

### 17.1 Cognitive Radio and Spectrum Sensing
[TO BE CONFIRMED: Add citations from project documentation]
- [Standard references on cognitive radio]
- [Key papers on spectrum sensing techniques]
- [IEEE 802.22 standards documentation]

### 17.2 Detection Theory
[TO BE CONFIRMED]
- Neyman-Pearson lemma and optimal detection
- Energy detection theory
- Receiver Operating Characteristic (ROC) analysis

### 17.3 5G and Waveform Analysis
[TO BE CONFIRMED]
- 5G NR waveform specifications
- OFDM and QAM modulation details
- 3GPP standards references

### 17.4 Filter Design and Signal Processing
[TO BE CONFIRMED]
- Wiener filter theory and application
- Adaptive filtering techniques
- [Additional signal processing references]

### 17.5 Hardware and Implementation
[TO BE CONFIRMED]
- USRP-2901 technical documentation
- LabVIEW USRP driver documentation
- Real-time signal processing implementation guides

---

## 18. Disclaimer / Academic Note

### 18.1 Academic Work
This project was developed as part of an undergraduate engineering curriculum in Electronics and Communication Engineering. It represents the technical work and learning outcomes achieved during the course duration and is intended for academic evaluation and professional portfolio purposes.

### 18.2 Experimental Validation
All reported results are based on:
- Simulations conducted with stated assumptions and parameter settings
- Hardware measurements under laboratory conditions
- [TO BE CONFIRMED: Field validation scope and extent]

### 18.3 Code Quality and Reproducibility
This repository aims to provide transparent documentation of methodology and implementation to enable:
- Reproduction of simulation results
- Verification of hardware measurements
- Independent validation by reviewers
- Future extension and improvement

### 18.4 Use of Tools and Resources
- MATLAB: University-licensed
- LabVIEW: University-licensed with USRP module
- USRP-2901: Academic research platform
- Third-party libraries and functions are documented and attributed

---

## 19. Repository Structure

```
enhanced-ncnp-5g-cognitive-radio/
│
├── README.md                          # This file
├── .gitignore                         # Git ignore file
│
├── docs/
│   └── project-overview.md            # Detailed project overview
│
├── src/
│   ├── matlab/
│   │   ├── signal_generation.m        # QAM signal generation
│   │   ├── ncnp_detector.m            # NCNP detector implementation
│   │   ├── energy_detector.m          # Energy detection algorithm
│   │   ├── wiener_filter.m            # Wiener filter implementation
│   │   ├── performance_analysis.m     # Pd/Pfa analysis
│   │   ├── roc_analysis.m             # ROC curve generation
│   │   └── main_simulation.m          # Main simulation driver
│   │
│   └── labview/
│       ├── USRP_Interface.vi          # USRP communication VI
│       ├── NCNP_Detector_RT.vi        # Real-time detector VI
│       ├── Data_Logger.vi             # Performance logging VI
│       └── UI_Dashboard.vi            # User interface VI
│
├── results/
│   ├── simulation_metrics.txt         # Summary statistics
│   └── [results data files]           # [TO BE ADDED]
│
├── figures/
│   ├── system_architecture.png        # System block diagram
│   ├── pd_vs_snr_curves.png          # Detection probability analysis
│   ├── roc_curves.png                # ROC curve comparison
│   ├── filter_comparison.png         # Filtered vs unfiltered
│   ├── wiener_filter_response.png    # Filter frequency response
│   └── [additional figures]          # [TO BE ADDED]
│
└── LICENSE                            # [TO BE CONFIRMED: MIT, Apache-2.0, etc.]
```

---

## 20. Getting Started

### 20.1 Prerequisites
- **MATLAB R2020a or later** (for simulation)
- **LabVIEW 2020 SP1 or later** (for hardware implementation)
- **USRP Hardware Driver (UHD)** compatible with USRP-2901
- **LabVIEW USRP Driver** module
- **Python 3.7+** (optional, for utility scripts)

### 20.2 Quick Start - Simulation Only
```bash
# Clone repository
git clone https://github.com/nandh-ini-p/enhanced-ncnp-5g-cognitive-radio.git
cd enhanced-ncnp-5g-cognitive-radio

# Run main simulation
cd src/matlab
matlab -r "main_simulation; exit"
```

### 20.3 Hardware Setup
[TO BE CONFIRMED: Hardware setup and configuration instructions]

---

## 21. Contact and Attribution

**Repository Owner**: [nandh-ini-p](https://github.com/nandh-ini-p)  
**Project Period**: [TO BE CONFIRMED: semester/year]  
**Institution**: [TO BE CONFIRMED: University name]  
**Department**: Electronics and Communication Engineering

For questions regarding this project, please open an issue in the repository.

---

**Last Updated**: [TO BE CONFIRMED: date]  
**Version**: 1.0.0
