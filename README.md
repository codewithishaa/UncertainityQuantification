# Uncertainty Quantification – Model V: High Inoculum Case 🌱📉

This repository presents our group project for the **ACM41000: Uncertainty Quantification** module at **University College Dublin (UCD)**. We model the spread of **stem canker disease** in potato crops using an extended version of the classical **SIR model** — known as **Model V – High Inoculum Density**, based on Gilligan et al. (1997).

## 🧪 Objective
To quantify uncertainty in the progression of plant disease under high infection pressure, and to identify key parameters influencing disease dynamics through:
- Parameter estimation
- Model fitting
- Local sensitivity analysis

---

## 🧩 Model Overview

We modeled disease dynamics using a system of ODEs, with compartments:
- **S** – Susceptible stems  
- **I** – Infected stems  
- **R** – Removed (dead) stems

Model V incorporates:
- **Nonlinear host response** (plant reaction to infection)
- **Decreasing infection force over time** as plants grow

### 🔢 Key Parameters
| Parameter | Description                  | Value     |
|-----------|------------------------------|-----------|
| `b`       | Stem production rate         | 1.467     |
| `κ`       | Carrying capacity            | 5.743     |
| `λ₀`      | Initial infection force      | 0.499     |
| `μ`       | Infection decay rate         | 0.247     |
| `α`       | Host response strength       | 2.106     |
| `γ`       | Saturation threshold         | 0.026     |
| `d`       | Death rate of infected stems | 0.058     |

---

## ⚙️ Implementation Details

- **Language**: R  
- **Packages**: `deSolve`, `ggplot2`, `optim` (L-BFGS-B)  
- **Approach**:
  - Fitted model using **least squares optimization**
  - Evaluated model fit using **Residual Sum of Squares (RSS)**
  - Conducted **local sensitivity analysis** by perturbing parameters (±30%)

---

## 📈 Results

- Final **RSS**: **3.33**, a significant improvement over the paper's reported **14.10**
- The model realistically captured the **rise and fall of infection**, and its sensitivity to stem production rate `b`
- **Higher `b`** values led to faster, more intense outbreaks; **lower `b`** slowed the infection curve

---

## 📊 Visual Insights
- Model predictions were compared to observed data using clear plots.
- Separate analyses were done for `S` and `I` compartments.
- Sensitivity plots illustrated how changes in `b` impact dynamics.

---

## 👩‍💻 Authors
- Isha Borgaonkar – [ishamborgaonkar@gmail.com](mailto:ishamborgaonkar@gmail.com)  

---

## 📌 Summary

This project demonstrates how mathematical modeling, parameter tuning, and sensitivity analysis can provide actionable insights into **plant disease management**. Model V with high inoculum settings proved to be both realistic and sensitive to key biological factors — offering strong predictive power.

