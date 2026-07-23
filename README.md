# SMART-Himalaya-LandDegradation

**Spatial Monitoring and Reporting Tool for Land Degradation in the Central Himalayas**

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXX)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GEE](https://img.shields.io/badge/Powered%20by-Google%20Earth%20Engine-blue)](https://code.earthengine.google.com/5fc025678a63c66f46652b7fd22d84d3)

---

## 📋 Overview

This repository contains the code, data, and documentation for the **Spatial Monitoring and Reporting Tool (SMART)**, a cloud-based web-geospatial framework designed to monitor land degradation in the central Himalayan region of Nepal.

The SMART platform integrates:
- **Google Earth Engine** for cloud-based remote sensing analysis
- **Google Colab** for machine learning and socio-environmental data integration
- **ArcGIS Pro** for final spatial refinement and visualization

**Study Area:** Dolakha District, Nepal (2001–2018)

---

## 🎯 Key Features

- **Multi-temporal Land Degradation Analysis** using Landsat 5 TM and Landsat 8 OLI imagery
- **Land Degradation Index (LDI)** integrating:
  - Barren Land Expansion (35% weight)
  - Vegetation Loss via NDVI decline (30% weight)
  - Slope Gradient (25% weight)
  - Riverbank Change (10% weight)
- **Random Forest Machine Learning** to model spatial correlations between infrastructure expansion, population density, and land cover change
- **Interactive web-GIS interface** for visualizing risk zonation maps
- **SDG Indicator 15.3.1** alignment for Land Degradation Neutrality monitoring

---

## 📁 Repository Structure

```
SMART-Himalaya-LandDegradation/
│
├── GEE_Scripts/
│   ├── 01_Image_Processing.js          # Landsat compositing and cloud masking
│   ├── 02_NDVI_BSI_Calculation.js      # Vegetation and bare soil indices
│   ├── 03_LDI_Weighted_Overlay.js      # Land Degradation Index computation
│   └── 04_Risk_Zonation_Export.js      # Risk classification and map export
│
├── Colab_Notebooks/
│   └── SMART_RF_Modeling.ipynb         # Random Forest ML with socio-environmental data
│
├── Data/
│   ├── boundaries/                     # District and VDC boundary shapefiles
│   ├── socio_env/                      # Census and ICIMOD vulnerability data
│   └── outputs/                        # Generated raster and vector files
│
├── docs/
│   ├── methodology.md                  # Detailed methodology document
│   ├── workflow_diagram.png            # SMART technical framework
│   └── user_guide.md                   # End-user instructions
│
├── results/
│   ├── figures/                        # Publication-ready figures
│   ├── maps/                           # Risk zonation maps (2001, 2018, change)
│   └── tables/                         # Summary statistics
│
├── LICENSE
├── README.md
├── requirements.txt                    # Python dependencies
└── CITATION.cff                        # Citation information
```

---

## 🚀 Getting Started

### Prerequisites

- **Google Earth Engine** account ([sign up here](https://earthengine.google.com/signup/))
- **Google Colab** access (free tier sufficient)
- **Python 3.8+** with packages listed in `requirements.txt`
- **ArcGIS Pro** (optional, for desktop refinement)

### Quick Start: GEE Application

1. **Open the GEE App directly:**
   ```
   https://[your-username].users.earthengine.app/view/smart-himalaya
   ```

2. **Or run scripts in GEE Code Editor:**
   ```javascript
   // Load the main analysis script
   var script = require('users/your-username/SMART-Himalaya-LandDegradation:GEE_Scripts/01_Image_Processing.js');
   ```

### Quick Start: Colab Notebook

1. Open the notebook in Google Colab:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/SMART-Himalaya-LandDegradation/blob/main/Colab_Notebooks/SMART_RF_Modeling.ipynb)

2. Authenticate with Earth Engine:
   ```python
   import ee
   ee.Authenticate()
   ee.Initialize()
   ```

---

## 📊 Land Degradation Index (LDI)

The LDI is calculated as:

```
LDI = 0.35(BE) + 0.30(NDVI_L) + 0.25(SL) + 0.10(RC)
```

Where:
- **BE** = Barren Land Expansion
- **NDVI_L** = NDVI decline (vegetation loss)
- **SL** = Slope Gradient
- **RC** = Riverbank Change

**Risk Classification:**
- Very Low (0–0.2)
- Low (0.2–0.4)
- Moderate (0.4–0.6)
- High (0.6–0.8)
- Very High (0.8–1.0)

---

## 📈 Results Summary

- Barren land expansion: **7% → 22%** of district area (2001–2018)
- Highest degradation along **new rural road corridors**
- **78%** of affected agrarian households reported productivity declines
- Degradation hotspots identified in communes with significant infrastructure development

> **Note:** Full results and figures are available in the `results/` directory and in the associated publication [citation].

---

## 🛠️ Data Sources

| Data Type | Source | Years |
|-----------|--------|-------|
| Landsat 5 TM | USGS | 2001 |
| Landsat 8 OLI | USGS | 2018 |
| SRTM DEM | NASA | 2000 |
| JRC Global Surface Water | European Commission | 1984-2020 |
| Population Census | CBS/Nepal | 2001, 2011 |
| Vulnerability Data | ICIMOD | Various |
| Agricultural Registry | MoALD/Nepal | Decadal |

---

## 📝 Citation

If you use this repository or the SMART tool in your research, please cite:

```bibtex
@article{thapa_smart_2026,
  title={Anthropogenic Pressures on Land Degradation in the Central Himalayas: Designing Spatial Monitoring and Reporting Tool (SMART)},
  author={Thapa, Pawan},
  journal={[Journal Name]},
  year={2026},
  doi={[DOI]}
}
```

**Software citation:**
```bibtex
@misc{thapa_smart_code_2026,
  author = {Thapa, Pawan},
  title = {SMART-Himalaya-LandDegradation: Spatial Monitoring and Reporting Tool for Himalayan Land Degradation},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/thapawan/SMART-Himalaya-LandDegradation}
}
```

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Google Earth Engine** for cloud computing infrastructure
- **ICIMOD** for vulnerability framework data
- **Central Bureau of Statistics, Nepal** for census data
- **Ministry of Agriculture and Livestock Development, Nepal** for agricultural registries
- **University of Alabama, Department of Geography & the Environment**

---

## 📧 Contact

**Pawan Thapa**  
Department of Geography & the Environment  
University of Alabama  
[Email: pthapa@ua.edu]  
[GitHub: thapawan](https://github.com/thapawan)

---

## 📚 Related Links

- [SMART Conservation Tools](https://smartconservationtools.org/) - Note: This project shares the SMART acronym but is a distinct, independent tool focused specifically on Himalayan land degradation monitoring.
- [Trends.Earth](https://trends.earth) - Another GEE-based land degradation monitoring platform
- [UNCCD SDG Indicator 15.3.1](https://www.unccd.int/actions/ldn-target-setting-programme/sdg-indicator-1531)

---

## ⚠️ Disclaimer

This tool is provided for research and monitoring purposes. While every effort has been made to ensure accuracy, users should validate results with ground-truth data where possible. The authors are not responsible for decisions made based on this tool's outputs.

---

*Last updated: July 2026*
```

---
