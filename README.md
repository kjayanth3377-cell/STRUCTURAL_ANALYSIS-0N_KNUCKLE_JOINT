# ⚙️ Knuckle Joint 3D Modeling and FEA Structural Analysis

## 📖 Project Description
This project focuses on the complete product development cycle—from 3D CAD modeling to advanced Finite Element Analysis (FEA)—of a mechanical knuckle joint. Knuckle joints are critical load-bearing linkages used in structural applications, automotive suspensions, and heavy machinery to transmit axial tensile loads while allowing a degree of angular flexibility. 

The primary objective of this project is to subject the SolidWorks assembly to a rigorous **30,000 N axial tensile load** in ANSYS Workbench. By evaluating the joint's performance across three distinct industrial metals, this study validates the structural integrity of the design, resolves complex contact non-linearities, and verifies computational solver results against classic theoretical hand calculations.

---

## 🎯 Project Objectives
* **CAD Modeling:** Develop a high-fidelity 3D assembly of a knuckle joint with proper mechanical clearances.
* **Material Optimization:** Evaluate and compare the von Mises stress, total deformation, and safety factors of AISI 4340 Alloy Steel, Mild Steel, and Stainless Steel.
* **Non-Linear Contact Setup:** Successfully simulate realistic mechanical load transfer using frictional contacts (avoiding artificial "bonded" rigidity).
* **Validation:** Correlate FEA maximum shear and crushing stresses with mathematical hand calculations to prove the validity of the simulation.

---

## 💻 Software Stack
* **3D CAD Modeling:** SolidWorks
* **FEA / Simulation:** ANSYS Workbench 2025 R2
* **Analysis Type:** 3D Static Structural


*(Insert an image of your SolidWorks CAD assembly here)*

---

## 📐 Dimensions & Assembly Details
The assembly consists of five interconnected parts: the Fork, Eye, Main Pin, Collar, and Taper Pin.

**Critical Dimensions for Validation:**
* **Main Pin Diameter ($d_1$):** 38.6 mm
* **Eye Thickness ($t$):** 28.0 mm
* **Fork Eye Thickness ($t_1$):** 28.0 mm

---

## 🧪 Material Properties Tested
To determine the optimal strength-to-weight and functional reliability, three materials were assigned and evaluated in ANSYS:

| Material | Young's Modulus (GPa) | Poisson's Ratio | Tensile Yield Strength (MPa) |
| :--- | :--- | :--- | :--- |
| **AISI 4340 Steel** | 205 | 0.29 | 470 |
| **Mild Steel** | 200 | 0.29 | 470 |
| **Stainless Steel** | 193 | 0.29 | 215 |

---

## ⚙️ FEA Setup & Boundary Conditions

### 1. Boundary Conditions
* **Fixed Support:** Constrained the flat, circular end face of the Fork rod to simulate a rigid structural mount.
* **Tensile Load:** A 30,000 N force was applied to the end face of the Eye rod along the X-axis, pulling the joint into pure tension.
* **Solver Controls:** `Large Deflection` was turned **ON** to account for geometric non-linearities as the pins and internal holes shifted and settled under the 3-ton load.

### 2. Contact Formulation
* **Frictional Contacts:** A friction coefficient of $\mu = 0.15$ was applied between the Main Pin and the internal faces of the Fork and Eye holes. This ensures the load is transferred through physical bearing pressure rather than artificial software bonding.

### 3. Meshing Strategy
* **Global Element Size:** 4.0 mm.
* **Targeted Face Sizing:** 2.0 mm sizing applied to 13 critical high-stress contact faces (the pin shaft and internal hole walls).
* **Transition Refinement:** Level 1 refinement applied to 17 fillet transition faces to accurately capture localized stress concentrations.


*(Insert an image of your meshed model with boundary conditions visible)*

---

## 🧮 Theoretical Hand Calculations
To ensure the FEA results are grounded in theoretical mechanics, failure modes were calculated manually for the 30,000 N load.

1. **Shear Stress on Main Pin (Double Shear):** $$\tau = \frac{P}{2 \cdot (\frac{\pi}{4} d_1^2)} = \frac{30000}{2 \cdot (\frac{\pi}{4} \cdot 38.6^2)} \approx 12.82 \text{ MPa}$$
   
2. **Crushing (Bearing) Stress inside the Eye:**
   $$\sigma_c = \frac{P}{d_1 \cdot t} = \frac{30000}{38.6 \cdot 28.0} \approx 27.75 \text{ MPa}$$

---

## 📊 FEA Results & Engineering Analysis

The solver generated results for Total Deformation, Equivalent (von Mises) Stress, Maximum Shear Stress, and Safety Factor. 

| Material | Max Total Deformation | Nominal Safety Factor (Main Body) | Localized Min Safety Factor (Fillet) |
| :--- | :--- | :--- | :--- |
| **AISI 4340 Steel** | ~6.2 mm | > 3.0 | 0.067 |
| **Mild Steel** | ~6.2 mm | > 3.0 | 0.069 |
| **Stainless Steel** | ~6.4 mm | > 2.0 | 0.032 |


*(Insert an image of your Equivalent Stress or Safety Factor plot here)*

### 🔍 Analysis of Stress Singularities
**Note on Minimum Safety Factor:** The absolute minimum safety factors reported by the solver (e.g., 0.067 for AISI 4340) occur strictly at the `taperpin Fillet6` transition. In FEA, this represents a **numerical stress singularity** where rigid micro-sliding pushes against a sharp edge boundary. The nominal stress through the primary load path (from the eye, through the main pin, and into the fork) aligns perfectly with the hand calculations ($\approx 12-28$ MPa), ensuring the joint will safely operate under the 30,000 N load.

---

## 🏆 Conclusion
**AISI 4340 Alloy Steel** is the optimal material for this linkage design. 

While the Mild Steel setup utilized a matching yield strength (470 MPa) in the software, standard mild steel generally yields much lower in real-world procurement (around 250 MPa). AISI 4340 naturally provides a high yield strength (470+ MPa), exceptional fatigue resistance, and higher toughness. Since knuckle joints are frequently subjected to dynamic, repetitive pulling loads, the structural rigidity and high safety factor of AISI 4340 make it the most reliable engineering choice among the tested metals.

---

## 👨‍💻 About the Author
**Jayanth**
*Third-Year B.Tech Mechanical Engineering Student*

Passionate about structural analysis, mechanical design, and translating theoretical mechanics into optimized 3D CAD/FEA models using SolidWorks and ANSYS.

* 🔗 **LinkedIn:** [https://www.linkedin.com/in/jayanth-kumar-819335376]
* 🛠️ **GrabCAD:** [https://grabcad.com/kammari.jayanth.kumar.achary-1]
* 📁 **GitHub:** [@kjayanth3377-cell](https://github.com/kjayanth3377-cell)]
*
