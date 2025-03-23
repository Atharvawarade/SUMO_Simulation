# Traffic Simulation Project: Baseline vs. Rain Conditions

This project simulates traffic and pedestrian behavior in **dry weather** (baseline) and **rainy weather** in Trafalgar Square. Below are simple steps to set up and run the simulations.

---

## 📂 Project Structure
Your project folder (`project-root/`) is organized as follows:
```
project-root/
├── config/          # Configuration files
├── data/            # Maps, weather data, and networks
├── scripts/         # Scripts to generate scenarios
├── output/          # Simulation results
├── scenarios/       # Vehicle and pedestrian routes
└── report/          # Charts, screenshots, and final report
```

---

## 🛠️ Setup Instructions

1. **Install SUMO** (if not already installed):
   - Download SUMO from [SUMO Official Website](https://www.eclipse.org/sumo/) and follow the installation guide.

2. **Place Videos in the Correct Folder**:
   - Copy the provided videos (`baseline_traffic.mp4` and `rain_traffic.mp4`) into the `project-root/report/screenshots/` folder.

---

## 🚦 How to Run the Simulations

### Step 1: Run the **Baseline (Dry Weather)** Simulation
1. **Open SUMO-GUI**:
   - Double-click the `SUMO-GUI` application on your desktop.
2. **Load the Baseline Configuration**:
   - Go to **File > Open Configuration**.
   - Navigate to `project-root/config/baseline.sumocfg` and select it.
3. **Start the Simulation**:
   - Click the **Start** button (▶️) in the bottom-right panel.
   - Watch vehicles and pedestrians move at normal speeds.

**Baseline Condition Video**:  
<video controls width="600">
  <source src="https://ik.imagekit.io/alky8omp4/Baseline_condition.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

### Step 2: Generate the Rain Scenario
1. **Run the Rain Generation Script**:
   - Open the `scripts` folder.
   - Double-click `generate_rain_scenario.py` (requires Python installed).  
     *This script uses real-time rain data to adjust vehicle and pedestrian behavior.*
   - Wait for the message: **"Rain scenario files generated successfully!"**

---

### Step 3: Run the **Rainy Weather** Simulation
1. **Reload SUMO-GUI** (if closed).
2. **Load the Rain Configuration**:
   - Go to **File > Open Configuration**.
   - Navigate to `project-root/config/rain_adaptive.sumocfg` and select it.
3. **Start the Simulation**:
   - Click **Start** (▶️).  
     *You’ll see slower vehicles, longer pedestrian wait times, and simulated rain effects.*

**Rain Condition Video**:  
<video controls width="600">
  <source src="./report/screenshots/rain_traffic.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

## 📊 What You’ll Observe
| Condition       | Vehicles              | Pedestrians          | Traffic Flow         |
|-----------------|-----------------------|----------------------|----------------------|
| **Baseline**    | Normal speed          | Quick crossings      | Smooth               |
| **Rain**        | Slower, cautious      | Longer wait times    | Congested            |

---

## ❓ Need Help?
Contact [Your Name/Email] for assistance.  
**Tip**: Always close and reopen SUMO-GUI when switching between scenarios!
