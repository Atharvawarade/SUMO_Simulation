
# 🌧️ SUMO Traffic Simulation with Rain-Adaptive Pedestrian Priority

[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![SUMO 1.15](https://img.shields.io/badge/SUMO-1.15.0-orange)](https://sumo.dlr.de/)
[![License MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A complete urban mobility simulation framework that dynamically adjusts pedestrian/vehicle behavior during rainfall in Trafalgar Square, London. Developed using SUMO, Python, and real-world weather data.

---

## 🧩 Features
- **Weather-Aware Traffic Control**: Dynamically modifies pedestrian crossing times + vehicle speeds based on rainfall intensity
- **Realistic Crowd Simulation**: Implements SUMO's social force model for pedestrians
- **Data Integration**: Uses historical rain data from Meteostat/NOAA
- **Performance Analytics**: Measures congestion, wait times, and traffic efficiency
- **Reproducible Scenarios**: Pre-configured baseline + rain-adaptive traffic models

---

## 📂 Project Structure
```plaintext
project-root/
├── data/                   # All input data
│   ├── osm/                # Raw OpenStreetMap files
│   ├── network/            # Processed SUMO road networks
│   └── weather/            # Rainfall datasets (CSV)
│
├── config/                 # SUMO configuration files
├── scenarios/              # Traffic scenarios
│   ├── baseline/           # Normal weather routes
│   └── rain/               # Rain-adaptive routes
│
├── scripts/                # Python automation scripts
├── output/                 # Simulation results
└── report/                 # Analysis reports + visuals
```

---

## ⚙️ Prerequisites
- [SUMO 1.15+](https://www.eclipse.org/sumo/)
- Python 3.8+
- Git

**Python Packages**:
```bash
pip install traci pandas matplotlib xmltodict
```

---

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/SUMO-Traffic-Simulation.git
cd SUMO-Traffic-Simulation
```

### 2. Set Up Environment
```bash
# Set SUMO_HOME (Windows)
setx SUMO_HOME "C:\Path\To\Sumo"
setx PATH "%PATH%;%SUMO_HOME%\bin"

# Verify installation
sumo-gui --version
```

---

## 🛠 Full Setup Guide

### Step 1: Generate SUMO Network
1. **Download OSM Data**:
   - Use [Overpass Turbo Query](https://overpass-turbo.eu/) for Trafalgar Square
   - Export as `data/osm/trafalgar.osm.xml`

2. **Convert to SUMO Network**:
```bash
netconvert --osm-files data/osm/trafalgar.osm.xml \
  -o data/network/trafalgar.net.xml \
  --sidewalks.guess true \
  --crossings.guess true
```

### Step 2: Generate Traffic Scenarios
```bash
# Generate baseline routes
python scripts/generate_routes.py \
  -n data/network/trafalgar.net.xml \
  -s scenarios/baseline

# Generate rain-adaptive routes
python scripts/generate_rain_scenario.py
```

---

## 🖥 Running Simulations

### Option 1: GUI Simulation (Visual)
**Baseline (No Rain)**:
```bash
sumo-gui -c config/baseline.sumocfg --pedestrian.model social
```

**Rain Scenario**:
```bash
sumo-gui -c config/rain_adaptive.sumocfg --pedestrian.model social
```

### Option 2: Headless Simulation (Fast)
```bash
sumo -c config/baseline.sumocfg --no-warnings
```

### Option 3: Advanced Control via TraCI
```bash
# Run adaptive simulation with weather integration
python scripts/traci_rain_adaptive.py
```

---

## 📊 Analyzing Results

### Key Output Files
- `output/baseline/tripinfo.xml`: Vehicle/pedestrian metrics (no rain)
- `output/rain/tripinfo.xml`: Rain scenario performance data

### Generate Comparative Charts
```bash
python scripts/analyze_results.py
```
**Outputs**:
- `report/charts/wait_times_comparison.png`
- `report/charts/congestion_levels.png`

---

## 🧪 Testing Framework
```bash
# Run unit tests
python -m pytest tests/

# Sample test output
============================= test session starts =============================
collected 5 items

tests/test_network.py ....                                               [80%]
tests/test_routes.py .                                                    [100%]
```

---

## 🚨 Troubleshooting

### Common Issues
**SUMO Path Errors**:
```bash
# Verify environment variables
echo %SUMO_HOME%
```

**Missing Pedestrians**:
```bash
# Check sidewalk generation
netedit data/network/trafalgar.net.xml
```

**Large File Pushing**:
```bash
# Remove historical emissions data
git filter-repo --path output/**/emissions.xml --invert-paths
```

---

## 🤝 Contributing
1. Fork the repository
2. Create feature branch:
```bash
git checkout -b feature/improved-rain-model
```
3. Commit changes:
```bash
git commit -m "Add enhanced rainfall adaptation logic"
```
4. Push to branch:
```bash
git push origin feature/improved-rain-model
```
5. Open pull request

---

## 📜 License
Distributed under MIT License. See `LICENSE` for details.

---

## 📬 Contact
**Author**: Atharva Warade  
**Email**: atharva@traffic-sim.com  
**LinkedIn**: [linkedin.com/in/atharvawarade]()

---

*🛠️ Happy Simulating! Let's build smarter cities together.*
```

This Markdown file:
1. Provides complete setup/execution instructions
2. Includes copy-paste ready commands
3. Shows visual hierarchy with emojis/headers
4. Covers both basic and advanced usage
5. Addresses common troubleshooting scenarios
6. Maintains professional formatting throughout

To use: 
1. Replace placeholder URLs/emails
2. Add actual screenshots to `report/screenshots/`
3. Customize contact/license info
