# EVRPTW-RL: Learning to Solve Electric Vehicle Routing Problems with Time Windows

This repository summarizes a team project from **MIE1630 @ University of Toronto**, where we applied **Reinforcement Learning (RL)** to solve the **Electric Vehicle Routing Problem with Time Windows (EVRPTW)** — a practical and complex variant of the VRP.

> 🔗 Full team codebase: [RL4EVRPTW](https://github.com/s33zhong/RL4EVRPTW)

> 📁 Code for result generation: in the `example/` folder — look for files starting with `EVRPTW`
 
> 📑 Report: [Download here](https://github.com/user-attachments/files/20830190/EV_Report.pdf)

## 📌 Problem Overview

EVRPTW tasks electric vehicles with visiting customers under time window and battery constraints. Key challenges:
- Battery-aware route planning  
- Time window feasibility  
- Charging station usage  
- Combinatorial explosion on large-scale instances

## 🚀 Solution Approaches

1. **MILP Baseline**
   - Built with Gurobi to solve small instances optimally
   - Modeled energy, time window, and routing constraints

2. **RL Solver with GNN Policy**
   - Used graph neural networks to encode problem instances
   - Applied RL to learn policies on larger EVRPTW graphs
   - Enforced feasibility using action masking


## 🧠 Results

| Instance             | MILP (Dist / Feas / Time) | RL Policy (Dist / Feas / Time) |
|----------------------|:-------------------------:|:------------------------------:|
| C10-S3-EV3           | 3.82 / 100% / 7.1s        | 4.26 / 100% / <0.01s           |
| C20-S3-EV3           | 5.66 / 98% / 56.7s        | 6.74 / 100% / <0.01s           |
| C50-S6-EV6           | 12.38 / 14% / 60.3s       | 12.45 / 100% / <0.01s          |
| C100-S12-EV12        | 23.41 / 1% / 60.5s        | 20.40 / 100% / <0.01s          |

✅ RL policy achieved **100× faster routing** while maintaining **100% feasibility** on large instances.


## 👨‍💻 Personal Contributions

- Developed **MILP baseline** using Gurobi; achieved 98–100% feasibility on small cases (≤20 nodes)
- Collaborated on **debugging RL pipeline**, fixing action masking and reward calculation bugs
- Built custom **visualization tool** to render directional EV routes with depot, customer, and station roles


## 📊 Route Visualization

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e4f2ddd-d936-4f86-80c2-1a32bc4002a5" alt="EV Route Visualization" width="700"/>
</p>

> EV routes showing depots (squares), customers (circles), and charging stations (triangles).  
> Arrows indicate direction; colors distinguish vehicles and routes.

## 📍 Notes

This repository highlights individual contributions and summarizes the team project. For full code and experiments, refer to the linked repo above.
