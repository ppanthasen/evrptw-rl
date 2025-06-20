# EVRPTW-RL: Learning to Solve Electric Vehicle Routing Problems with Time Windows

This repository presents a summary of a team project from the graduate course **MIE1630 at the University of Toronto**, focusing on applying **Reinforcement Learning (RL)** to solve the **Electric Vehicle Routing Problem with Time Windows (EVRPTW)** — a complex and practical variant of the classic VRP.  
While the team codebase is [hosted separately](https://github.com/s33zhong/RL4EVRPTW), this landing page outlines the project architecture, key results, and my individual contributions.


## 📌 Problem Overview

EVRPTW involves dispatching electric vehicles to serve a set of customers with delivery time windows and limited battery capacity. Challenges include:

- Battery-aware route planning
- Time window constraints
- Charging station utilization
- Combinatorial complexity on large-scale instances


## 🚀 Our Approach

We implemented and compared two solution methods:

1. **MILP Baseline**  
   - Built using Gurobi to solve small instances optimally  
   - Incorporated energy, time window, and route constraints

2. **RL-Based Solver with GNN Policy**  
   - Learned policies using reinforcement learning for large-scale EVRPTW instances  
   - Utilized graph neural networks to encode depot, customers, and charging stations  
   - Used action masking to enforce feasibility


## 🧠 Key Results

| Instance             | MILP (Distance / Feasibility / Runtime) | RL Policy (Distance / Feasibility / Runtime) |
|----------------------|:---------------------------------------:|:--------------------------------------------:|
| C10-S3-EV3           |  3.82 / 100% /  7.1 s                   |  4.26 / 100% / <0.01 s                       |
| C20-S3-EV3           |  5.66 /  98% / 56.7 s                   |  6.74 / 100% / <0.01 s                       |
| C50-S6-EV6           | 12.38 /  14% / 60.3 s                   | 12.45 / 100% / <0.01 s                       |
| C100-S12-EV12        | 23.41 /   1% / 60.5 s                   | 20.40 / 100% / <0.01 s                       |

✅ **RL-based policy achieved full feasibility with 100x faster inference** on large-scale problems.

## 🔧 Personal Contribution

- Developed the **MILP baseline** using Gurobi, achieving 98–100% feasibility on small instances (≤20 nodes)  
- Collaborated on **debugging and refining the GNN-based RL policy**, including:
  - Fixing action masking to prevent invalid moves (e.g., revisiting depot without time)
  - Correcting reward computations to reflect actual travel distances  
- Designed and implemented **visualization tools** for analyzing EV routes using directional, color-coded graphs


## 📊 Result Visualization

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e4f2ddd-d936-4f86-80c2-1a32bc4002a5" alt="EV Route Visualization" width="700"/>
</p>

> EV routes showing depot (square), customers (circles), and charging stations (triangles).  
> Arrows indicate movement direction. Color reflects routes and nodes.


## 📁 Team Codebase

🔗 Full implementation is available [here](https://github.com/s33zhong/RL4EVRPTW)

🗂️ To view the result-generating code, check the `example/` folder — files starting with `EVRPTW` demonstrate training, evaluation and visualization steps.

📑 Full project report available [here](https://github.com/user-attachments/files/20830028/EV_Report.pdf) for additional details.

## 📍 Notes

> This repo serves to highlight individual contributions and summarize project outcomes.  
> For full details, please refer to the linked repository above.
