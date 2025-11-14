# Indoor Sharing in the Mid-Band: Neutral-Host, Cellular Macro & Wi-Fi Performance Dataset

[![DOI](https://img.shields.io/badge/DOI-10.1109%2FCCNC-blue)](https://ieeexplore.ieee.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

This repository contains the reproducible dataset and measurement methodology from our IEEE CCNC 2025 paper: **"Indoor Sharing in the Mid-Band: A Testbed Evaluation of Neutral-Host, Cellular Macro & Wi-Fi"**.

## Overview

This work presents a comprehensive three-way comparative analysis of mid-band spectrum (1-6 GHz) indoor wireless performance across:
- **CBRS-based Neutral-Host (NH) networks** (3.5 GHz)
- **Public MNO macro cellular networks** (4G/5G)
- **Enterprise Wi-Fi 6** (802.11ax)

The measurements were conducted in a large big-box retail store (~187,000 ft²) and surrounding outdoor areas (~305,000 ft²) between February 24-26, 2025.

## Key Findings

- **Coverage Efficiency**: NH achieves full indoor coverage with only 6 CBSDs vs. 65 APs required for Wi-Fi
- **Building Loss**: Median 26.6 dB building loss ensures interference-free coexistence with outdoor incumbents
- **Throughput Gains**: NH provides 1.44×-1.62× DL and 4.33×-13× UL normalized throughput improvements over macro deployments
- **Application Performance**: NH achieves 5.05× HTTP DL throughput improvement over Wi-Fi despite using only 40 MHz vs. 20 MHz for Wi-Fi
- **Aggregated Performance**: 2.08× PHY-layer DL throughput gain over 5G macro indoors (40 MHz NH vs. 225 MHz 5G)

## Dataset

The dataset includes **221,396** cellular datapoints and **570,803** Wi-Fi beacon measurements across:

### Cellular Measurements (QualiPoc)
- Radio reports (RSRP, RSRQ, PCI, ARFCN, bandwidth, SCS)
- Physical layer throughput (PDSCH/PUSCH)
- Normalized throughput metrics
- Application layer HTTP throughput
- UE transmit power
- GPS coordinates

### Wi-Fi Measurements (SigCap)
- BSSID and SSID information
- RSSI measurements
- Channel assignments
- AP transmit power
- Beacon data

## Repository Structure
```
.
├── data/
│   ├── cellular/          # QualiPoc measurements
│   │   ├── radio_reports/
│   │   ├── throughput/
│   │   └── application_layer/
│   ├── wifi/              # SigCap measurements
│   │   └── beacon_data/
│   └── metadata.json      # Deployment configuration details
├── scripts/
│   ├── data_processing/   # Data cleaning and preprocessing
│   ├── analysis/          # Analysis scripts for figures
│   └── visualization/     # Plotting utilities
├── figures/               # Generated figures from the paper
├── docs/
│   ├── measurement_methodology.md
│   └── deployment_parameters.md
├── paper/
│   └── 2025_IEEE_CCNC_NH_Arkansas.pdf
├── LICENSE
└── README.md
```

## Deployment Details

### Neutral-Host Network
- **Technology**: 4G LTE TDD in CBRS band (b48)
- **Devices**: 6 CBSDs with omnidirectional antennas
- **TX Power**: 24 dBm, Antenna Gain: 3 dBi
- **Channels**: 5 unique 20 MHz channels (3560-3690 MHz)
- **Carrier Aggregation**: Up to 2 channels (40 MHz)

### Enterprise Wi-Fi
- **Standard**: Wi-Fi 6 (IEEE 802.11ax)
- **Access Points**: 65 (5 GHz) + 12 (2.4 GHz)
- **Channel Width**: 20 MHz
- **TX Power**: 10-19 dBm (5 GHz), 14 dBm (2.4 GHz)

### MNO Macro Networks
- **4G Bands**: Low-band (600-850 MHz) and mid-band (1700-2300 MHz)
- **5G Bands**: Low-band (600 MHz), mid-band (1900, 2500, 3700 MHz)
- **Outdoor deployment** with indoor coverage via building penetration

## Citation

If you use this dataset or findings in your research, please cite:
```bibtex
@article{palathinkal2025indoor,
  title={Indoor Sharing in the Mid-Band: A Performance Study of Neutral-Host, Cellular Macro, and Wi-Fi},
  author={Palathinkal, Joshua Roy and Rochman, Muhammad Iqbal and Sathya, Vanlin and Yavuz, Mehmet and Ghosh, Monisha},
  journal={arXiv preprint arXiv:2506.04974},
  year={2025}
}
```

## Related Work

This work extends our previous analysis:
- [M. I. Rochman et al., "Neutral-hosts in the shared mid-bands: Addressing indoor cellular performance," *IEEE DySPAN*, 2025.](https://ieeexplore.ieee.org/document/11115898)

## Authors

- **Joshua Roy Palathinkal** - University of Notre Dame
- **Muhammad Iqbal Rochman** - University of Notre Dame
- **Vanlin Sathya** - Celona, Inc.
- **Mehmet Yavuz** - Celona, Inc.
- **Monisha Ghosh** - University of Notre Dame

## Contact

For questions or collaboration inquiries:
- Email: jpalathi@nd.edu

## Acknowledgments

This work is supported by NSF grant CNS-2229387.

## License

This dataset is released under the MIT License. See [LICENSE](LICENSE) for details.

---

**Keywords**: CBRS, Neutral-Host, 5G, Wi-Fi 6, Indoor Coverage, Spectrum Sharing, Mid-Band, Private Networks
