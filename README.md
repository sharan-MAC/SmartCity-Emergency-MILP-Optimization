# Optimization of Smart Public Service Model with Extended Resource Variables

![Optimization Flow](https://img.shields.io/badge/Optimization-MILP-blue)
![Solver](https://img.shields.io/badge/Solver-LINDO%20/%20LINGO-green)
![Field](https://img.shields.io/badge/Field-Operations%20Research-orange)

## 📌 Project Overview
This repository contains a high-fidelity **Mixed-Integer Linear Programming (MILP)** model designed to optimize multi-agency emergency responses in a Smart City environment. 

Building upon the foundational research of **Pardede et al. (2024)**, this project extends the resource matrix by adding:
1.  **A 5th Agency:** Rapid-Response Motorcycle Ambulance (RRMA).
2.  **A 6th Victim Location:** Increasing decision complexity to 180 binary variables.
3.  **Tiered Response Logic:** Offloading low-acuity medical tasks to high-mobility units.

## 🚀 Key Features
* **6x6x5 Decision Matrix:** Synchronizes 5 agencies across 6 locations simultaneously.
* **Sub-tour Elimination:** Implements Miller-Tucker-Zemlin (MTZ) constraints to ensure valid routing.
* **Sensitivity Analysis:** Evaluates system degradation (latency increase) during node failure (e.g., Hospital decommissioning).
* **Shadow Price Analysis:** Identifies resource bottlenecks (Fire Brigade saturation) to guide municipal investment.

## 📊 Results Summary
* **Global Optimum (Z):** 169.0000 minutes.
* **Efficiency Gain:** 22.5% improvement over "Nearest Neighbor" (Greedy) dispatch.
* **Resiliency Buffer:** Tiered units provide a 15.5% delay reduction during primary hub failure.

## 🛠 Model Structure
The model is governed by **218 constraints**, categorized into:
- **Demand Satisfaction:** Every victim $j$ receives exactly 1 unit from each agency $s$.
- **Supply Constraints:** Dispatch cannot exceed regional personnel census ($N=362$).
- **Binary Restriction:** All variables $x_{ij} \in \{0, 1\}$.

## 📂 Repository Contents
* `/Model`: Contains the `.LTX` or `.LNB` files for LINDO/LINGO.
* `/Paper`: The IEEE-formatted research paper (PDF and LaTeX source).
* `/Data`: The personnel census and travel time matrices.

## 📝 How to Run the Solver
1. Install **LINDO API** or **LINGO**.
2. Open the file in `/Model/Emergency_Dispatch.ltx`.
3. Run the **Branch-and-Bound** command.
4. Execute the `RANGE` command to view **Shadow Prices** and **Sensitivity Analysis**.

## 🎓 Academic Reference
This project was developed as an extension of:
> *Pardede, A. M. H., et al. (2024). "Optimization of Smart Public Service Model with Limited Resources Using Linear Programming." Journal of Theoretical and Applied Information Technology (JATIT).*

## 📧 Contact
**[Your Name]** Department of Computer Science & Engineering  
[Your Institution]
