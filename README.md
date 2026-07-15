# 🏛️ Real-Time Upfront Embodied Carbon Auditing (AusCarbonCalc)

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-Rhino%20%7C%20Grasshopper-orange.svg)
![Language](https://img.shields.io/badge/Language-IronPython-yellow.svg)

## 📌 Overview
**AusCarbonCalc** is an open-source, object-oriented parametric compliance framework integrated directly within the Rhino 8 / Grasshopper environment. Calibrated against the **Australian National Construction Code (NCC 2025)** and localized **AusLCI carbon coefficient registries**, this tool empowers architects and researchers to execute real-time embodied carbon ($EC_u$) telemetry at Phase 0 conceptual massing.

By utilizing a robust IronPython core, the tool calculates total structural carbon footprints with execution latencies of `< 12 ms` and actively visualizes the compliance state via live environmental telemetry.

## 👥 Authors & Core Developers
This framework was developed through a cross-disciplinary collaboration bridging advanced systems architecture and sustainable environmental design:
*   **Mohsen Javdan Fard** *(Lead Systems Architect & Developer)*: Conceptualized the algorithmic architecture, developed the fail-safe IronPython data pipelines, and constructed the visual programming logic.
*   **Faezeh Akbari Nikjeh** *(Architectural & Sustainability Researcher)*: Formulated the LCA methodology, conducted NCC compliance research, established the carbon thresholds, and led the empirical validation against global EC3 benchmarks.

## ⚙️ Mathematical Core & Logic
The algorithmic engine computes upfront embodied carbon dynamically by reading pure mass data:
$$EC_u = \sum (V_n \times \rho_n \times CF_n)$$

**Baseline Configurations:**
*   **Absolute Carbon Budget (Threshold):** `15,000.0 kg CO2-e`
*   **Standard Concrete CF:** `320.0 kg CO2-e/m³`
*   **Structural Steel CF:** `800.0 kg CO2-e/m³`
*   **Timber / CLT CF:** `-400.0 kg CO2-e/m³` (Biogenic Sink)

## 🚀 Workflow & User Instructions
To maintain absolute transparency for academic peer review, the Grasshopper script is deliberately **un-clustered**, allowing users and reviewers to inspect the data flow from Geometry extraction to the Python logic core.

### How to run the simulation:
1. Open `src/farnsworth_base.3dm` in Rhino.
2. Launch Grasshopper and open `src/auscarboncalc_core.gh`.
3. The geometry is pre-linked to the initial `Mesh` parameter.
4. Use the `Value List` component to toggle between structural materials (Concrete, Steel, Wood).
5. The total volume and carbon footprint will instantly update in the yellow reporting panel.

> ⚠️ **CRITICAL VISUALIZATION NOTE:** 
> Due to Grasshopper's native rendering pipeline and the transparent nature of this script, **you must click on and select the primary `Mesh` component** in the Grasshopper canvas to activate the visual telemetry. 
> *   When the `Mesh` component is selected, the Rhino viewport will accurately render the building as **Green (Compliant)** if the carbon is under 15,000 kg, or **Red (Non-Compliant)** if the limit is breached.

## 📂 Repository Structure
*   `/src`: Contains the primary Rhino model (`.3dm`) and Grasshopper definition (`.gh`).
*   `/assets`: Contains high-resolution validation screenshots (Green/Red compliance states).
*   `/docs`: Contains the draft manuscript and associated academic documentation.

## 📄 License
This project is licensed under the MIT License - ensuring open-access knowledge sharing for the sustainable architecture community.
