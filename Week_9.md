

# **VSDBabySoC – Complete Physical Design Flow (Week 1–9 Documentation)**

This repository contains the complete end-to-end implementation of **VSDBabySoC**, from RTL to **post-layout GDS**, including all experiments, logs, analysis, and custom modifications.

---

## **📌 Project Overview**

VSDBabySoC is a simplified System-on-Chip (SoC) used for learning full ASIC Physical Design using **OpenLane** and **Sky130 PDK**.
This documentation covers the entire journey:

✔ Architecture & RTL
✔ Synthesis
✔ Floorplanning
✔ Placement
✔ Clock Tree Synthesis
✔ Routing
✔ SPEF Extraction
✔ Post-Layout STA
✔ Final GDS Export

All screenshots include my Unix terminal username as required.

---

# **WEEK-WISE DOCUMENTATION**

---

## **🟦 Week 1 – Architecture & RTL Setup**

* Understood VSDBabySoC architecture, sub-blocks (babySoC top, pwm, clk_gen, etc.)
* Setup OpenLane + Sky130 PDK
* Verified RTL functionality using Iverilog/GTKWave
* Added screenshots of simulations and RTL structure

---

## **🟩 Week 2 – Synthesis**

* Ran `run_synthesis` in OpenLane
* Collected key metrics:

  * Number of cells
  * Combinational vs sequential logic
  * Worst Negative Slack
  * Critical paths
* Fixed minor warnings
* Added synthesis logs and reports as screenshots
* Checked mapped netlist in Yosys

---

## **🟨 Week 3 – Floorplanning**

* Generated die area, core area, pin placements
* Verified power distribution network (PDN)
* Ensured aspect ratio meets routing needs
* Included screenshots for:
  ✔ DEF
  ✔ floorplan density
  ✔ pin placements

---

## **🟥 Week 4 – Placement (Global + Detailed)**

* Performed global and detailed placement
* Removed high-fanout nets using buffering
* Checked placement legality
* Captured:
  ✔ Congestion map
  ✔ Placement DEF
  ✔ Cell distribution

---

## **🟪 Week 5 – Clock Tree Synthesis**

* Generated clock tree with balanced skew
* Verified:
  ✔ Clock buffers insertion
  ✔ Skew and latency
  ✔ CTS report
* Ensured hold/setup checks remained acceptable

---

## **🟫 Week 6 – Routing (Global + Detailed)**

* Used FastRoute + TritonRoute
* Fixed DRC violations
* Added routing layer usage screenshots
* Verified metal density and connectivity
* Obtained timing-clean routed netlist

---

## **🟧 Week 7 – SPEF Extraction**

* Extracted parasitics using `run_parasitics_sta`
* Generated:
  ✔ SPEF file
  ✔ extracted.sdf
* Included terminal logs and extracted RC values
* Prepared design for post-layout STA

---

## **🟩 Week 8 – Post-Layout STA**

* Performed STA using OpenSTA and SPEF
* Compared pre-layout vs post-layout timing
* Identified impact of RC parasitics
* Captured:
  ✔ Worst path delays
  ✔ Setup/Hold slack
  ✔ Clock path timing
  ✔ Timing violation fixes

---

## **🟦 Week 9 – Final Documentation & GDSII**

* Consolidated all results
* Exported final **GDSII**
* Checked layout in Magic / KLayout
* Verified final checks:
  ✔ DRC clean
  ✔ LVS correct
  ✔ Antenna violations fixed
* Uploaded all screenshots with username visible
* Created this complete GitHub documentation

---

# **⭐ Unique Experiments & Contributions**

### **1️⃣ Custom Synthesis Script Tweaks**

* Modified Yosys TCL to reduce negative slack
* Improved cell mapping via custom constraints
  **Why:** Enhance timing closure
  **Impact:** Reduced WNS and improved critical path

### **2️⃣ Custom Floorplan Adjustments**

* Modified DIE_AREA and CORE_UTILIZATION
  **Why:** Reduce congestion before placement
  **Impact:** Routing became smoother, fewer DRC errors.

### **3️⃣ Manual LEF/LIB Edits**

* Updated custom LEF pin directions for proper routing
  **Why:** To fix routing disconnect issues
  **Impact:** Successful global + detailed routing

### **4️⃣ Experimental STA Checks**

* Added custom TCL scripts to automate worst-path extraction
  **Why:** Faster debug
  **Impact:** Easier timing closure during routing/CTS.

---
