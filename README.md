# Lid Driven Cavity Flow Study (OpenFOAM)

## 📖 Project Overview
This repository contains an OpenFOAM-based CFD study of the **2D Lid-Driven Cavity Flow** problem, covering a range of **Reynolds numbers (Re)** from laminar to turbulent regimes.

The top wall (lid) moves with a constant velocity, while the other three walls are stationary with **no-slip boundary conditions**. The study investigates how the flow structure, vortex formation, and velocity profiles change with increasing Reynolds number.

---

##  Case Setup
- **Geometry**: 2D square cavity  
- **Reynolds numbers studied**: Re = 100, 1000 (laminar), Re = 5000, 10,000 (turbulent RANS)  
- **Solvers**:  
  - Laminar: `incompressibleFluid`  
  - Turbulent: `incompressibleFluid` (with  `k-omega`)
- **Boundary Conditions**:  
  - Lid (top wall): `fixedValue` velocity `(U, 0, 0)`  
  - Other walls: `noSlip`  
  - Turbulent cases include fields: `k`, `epsilon`, `omega`, `nut`, etc.  

---

##  Project Structure
```
LidDrivenCavity-OpenFOAM/
 ├── cases/                         # Different Re number cases
 │   ├── Re100/                     # Example: Re = 100 (laminar)
 │   │   ├── 0/
 │   │   ├── constant/
 │   │   ├── system/
 |   |── Re1000/                    # Example: Re = 1000 (laminar)
 │   │   ├── 0/
 │   │   ├── constant/
 │   │   ├── system/
 │   ├── Re5000/                    # Example: Re = 5000 (turbulent RANS)
 │   │   ├── 0/
 │   │   ├── constant/
 │   │   ├── system/
 │   │
 │   ── Re10000/                    # Example: Re = 10000 (turbulent RANS)
 │   │   ├── 0/
 │   │   ├── constant/
 │   │   ├── system/    
 ├── results/                       # Processed results (plots/images)
 │   ├── centerline_Ux_profiles.png
 │   ├── centerline_Uy_profiles.png
 │   ├── Re100_streamlines.png
 │   ├── Re1000_streamlines.png
 │   ├── Re5000_streamlines.png
 │   ├── Re10000_streamlines.png
 ├── README.md
 └── .gitignore
```
 
##  How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<username>/LidDrivenCavity-OpenFOAM.git
   cd LidDrivenCavity-OpenFOAM/cases/Re500
   ```
2. Clear any previous results:
   ```bash
   foamListTimes -rm
   ```
3. Run the case: ( shows a live log in the terminal and also saves one in directory)
   ```bash
   foamRun | tee log
   ```
   
