# NACA 4412 Wing Static Structural Analysis (FEA)

## 📌 Project Overview
This repository contains the 3D Static Structural (Finite Element Analysis - FEA) study of a **NACA 4412** wing structure under aerodynamic lift loading. The pressure load applied in this analysis was previously derived from CFD simulations and theoretical Python lifting-line calculations.

---

## 🛠️ Key Technical Features
* **Wing Profile:** NACA 4412
* **Wing Span ($L$):** $1.25\text{ m}$ ($1250\text{ mm}$)
* **Material:** Aluminum Alloy
  * **Young's Modulus ($E$):** $71\text{ GPa}$
  * **Poisson's Ratio ($\nu$):** $0.33$
  * **Yield Strength ($\sigma_y$):** $\approx 250\text{ MPa}$
* **Simulation Tool:** ANSYS Mechanical (Static Structural)

---

## ⚙️ Boundary Conditions & Meshing

1. **Meshing Strategy:**
   * **Physics Preference:** Mechanical
   * **Element Size:** $15\text{ mm}$ ($1.5 \times 10^{-2}\text{ m}$)
   * Smooth transition surface mesh tailored for airfoil curvature.

2. **Boundary Conditions:**
   * **Fixed Support (Ankastre Mesnet):** Applied to the root surface ($y = 0$), constraining all 6 degrees of freedom ($u_x = u_y = u_z = 0$).
   * **Aerodynamic Pressure:** Applied as a positive normal force ($+Z$ direction) on the lower surface.
   * **Magnitude:** $1569.53\text{ Pa}$ (derived from aerodynamic lift analysis).

<img width="1917" height="813" alt="Ekran görüntüsü 2026-07-22 175234" src="https://github.com/user-attachments/assets/0fdd89de-8e72-49c3-9dc4-d25b132779c3" />


---

## 📊 Results & Structural Evaluation

| Parameter | Value | Location / Critical Note |
| :--- | :--- | :--- |
| **Max. Equivalent Stress ($\sigma_{\max}$)** | **$17.87\text{ MPa}$** | Wing Root (Fixed Boundary Junction) |
| **Min. Equivalent Stress ($\sigma_{\min}$)** | **$992.36\text{ Pa}$** | Wing Tip |
| **Max. Total Deformation** | **$5.69\text{ mm}$** | Wing Tip |
| **Safety Factor ($\text{FoS}$)** | **$\approx 14.0$** | $\text{FoS} = \frac{\sigma_y}{\sigma_{\max}} = \frac{250}{17.87}$ |

### Equivalent (von-Mises) Stress Distribution
<img width="1622" height="582" alt="Ekran görüntüsü 2026-07-22 181310" src="https://github.com/user-attachments/assets/cd9d367f-de26-4564-9a33-fa9597b4bb17" />


### Total Deformation Distribution
<img width="1622" height="578" alt="Ekran görüntüsü 2026-07-22 181258" src="https://github.com/user-attachments/assets/6d4a5725-877e-481a-949c-13f758118556" />


---

## 🔍 Key Engineering Findings

* **Bending Moment Correlation:** In agreement with Euler-Bernoulli beam theory ($M = F \cdot L$), maximum Von Mises stress occurs at the root of the cantilevered wing ($17.87\text{ MPa}$).
* **Elastic Safety:** The maximum stress remains significantly below the material yield strength ($250\text{ MPa}$), yielding a high safety factor ($\text{FoS} \approx 14$). The structure operates fully within the linear elastic regime under standard steady-flight $1g$ loading.
