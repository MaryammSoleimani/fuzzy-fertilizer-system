# Fuzzy Inference System for Agricultural Fertilizer Recommendation 🌱


> 📓 **Note:** This project is implemented as a **Jupyter Notebook** 
> (main.ipynb). You can run it in Jupyter, VS Code, or PyCharm Professional.

A **Mamdani-type Fuzzy Inference System (FIS)** implementation that recommends 
the optimal fertilizer amount for agriculture based on soil conditions and plant type.

## 📌 Overview
This project is part of the **Computational Intelligence Fundamentals** course 
(Fuzzy Logic) at the Faculty of Electrical and Computer Engineering, 
University of Zanjan.

**Goal:** Design a fuzzy system that takes soil and plant characteristics as input 
and outputs a recommended fertilizer amount.

## 🔧 Inputs & Output

| Variable | Type | Range |
|----------|------|-------|
| Soil Type | Input | 0 – 10 |
| Soil Moisture | Input | 0 – 100 |
| Plant Type | Input | 0 – 10 |
| Fertilizer Amount | Output | 0 – 100 |

## 🧠 System Architecture
### Membership Functions

- **Soil Type:** Sandy (`zmf`), Loamy (`gbell`), Clay (`smf`)
- **Moisture:** Low (`zmf`), Medium (`gbell`), High (`smf`)
- **Plant Type:** Low / Medium / High Demand
- **Fertilizer:** Low (`zmf`), Medium (`gbell`), High (`smf`)

### Rule Base
A total of **16 fuzzy rules** are defined, e.g.:

> IF soil is Sandy AND moisture is Low AND plant is Low-demand 
> THEN fertilizer is High

### Inference Pipeline
1. **Fuzzification** — convert crisp inputs into membership degrees
2. **Antecedent (Min)** — combine conditions using the Min operator
3. **Implication (Mamdani Min)** — clip output MFs with rule firing strength
4. **Aggregation (Maximum)** — combine all rule outputs
5. **Defuzzification (Centroid)** — convert the fuzzy output into a crisp value

## 📊 Example Run

soil_input = 8       # Clay soil
moisture_input = 40  # Medium moisture
plant_input = 3      # Low-demand plant

Output: Recommended fertilizer ≈ 29.79
📈 Visual Outputs
1.Membership function plots for every input and output variable
2.Per-rule output plots and the final aggregated fuzzy set
