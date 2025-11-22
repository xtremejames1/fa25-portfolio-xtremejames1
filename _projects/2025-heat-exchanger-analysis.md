---
layout: project
title: Heat Exchanger Performance Analysis
description: Comparative analysis of parallel and counter flow heat exchangers
technologies: [Thermodynamics, Heat Transfer, MATLAB, Data Analysis]
image: /assets/images/temperature-profiles.png
---

# Heat Exchanger Performance Analysis: Parallel vs Counter Flow

**ENGRD 2210 - Thermodynamics Portfolio Project**
*James Xiao*
*Cornell University, Fall 2025*

---

## Executive Summary

This analysis compares heat exchanger performance in parallel and counter flow configurations. Experimental results demonstrate that counter flow operation achieves **45% greater temperature rise** in the cold stream (16.8°C vs 11.6°C) and **8.9% higher effectiveness** (63.4% vs 58.2%) compared to parallel flow under similar conditions.

---

## 1. Introduction

### Heat Exchanger Fundamentals

A heat exchanger transfers thermal energy between two fluids at different temperatures without mixing them. This device is critical in applications including automotive cooling systems, power plant condensers, HVAC systems, and chemical processing.

The heat exchanger studied consists of two independent flow circuits (hot and cold) with four ports. It can operate in two configurations:
- **Parallel Flow**: Both fluids flow in the same direction
- **Counter Flow**: Fluids flow in opposite directions

---

## 2. Experimental Setup

### Test Conditions

#### Parallel Flow Configuration

| Parameter | Value |
|-----------|-------|
| Hot inlet (T₁) | 45.0°C |
| Hot outlet (T₂) | 22.9°C |
| Cold inlet (T₃) | 7.0°C |
| Cold outlet (T₄) | 18.6°C |
| Flow condition | ṁ_cold > ṁ_hot |

#### Counter Flow Configuration

| Parameter | Value |
|-----------|-------|
| Hot inlet (T₁) | 45.0°C |
| Hot outlet (T₂) | 23.7°C |
| Cold inlet (T₃) | 11.4°C |
| Cold outlet (T₄) | 28.2°C |
| Flow condition | ṁ_cold > ṁ_hot |

---

## 3. System Diagrams

### Parallel Flow Configuration

<div class="diagram-container">
  <img src="{{ '/assets/images/parallel-flow-diagram.png' | relative_url }}" alt="Parallel Flow System Diagram">
  <p><em>Figure 1: System diagram showing parallel flow configuration with control volume boundary (green dashed line). Both hot and cold streams enter from the left and exit on the right, flowing in the same direction.</em></p>
</div>

### Counter Flow Configuration

<div class="diagram-container">
  <img src="{{ '/assets/images/counter-flow-diagram.png' | relative_url }}" alt="Counter Flow System Diagram">
  <p><em>Figure 2: System diagram showing counter flow configuration. Hot stream flows left to right while cold stream flows right to left, maximizing temperature differential throughout the heat exchanger.</em></p>
</div>

### Temperature Profiles

<div class="diagram-container">
  <img src="{{ '/assets/images/temperature-profiles.png' | relative_url }}" alt="Temperature Profiles">
  <p><em>Figure 3: Temperature profiles along the heat exchanger length for both configurations. The yellow shaded area represents the driving temperature difference (ΔT) available for heat transfer. Note the larger and more uniform ΔT in counter flow configuration.</em></p>
</div>

---

## 4. Thermodynamic Analysis

### Assumptions

1. Steady-state operation
2. Negligible kinetic and potential energy changes
3. Adiabatic outer walls (Q̇_loss ≈ 0)
4. Incompressible flow with constant properties
5. No work interactions

### Mass Balance

For steady flow:

$$\dot{m}_{in} = \dot{m}_{out} \text{ (for each stream)}$$

### Energy Balance

First Law of Thermodynamics for the heat exchanger control volume:

$$\dot{m}_h(h_1 - h_2) = \dot{m}_c(h_4 - h_3)$$

For liquid water with constant $c_p \approx 4.18 \text{ kJ/(kg·K)}$:

$$\dot{Q}_{hot} = \dot{m}_h \cdot c_p \cdot (T_1 - T_2)$$

$$\dot{Q}_{cold} = \dot{m}_c \cdot c_p \cdot (T_4 - T_3)$$

**Energy balance**: $\dot{Q}_{hot} = \dot{Q}_{cold}$

---

## 5. Quantitative Analysis

### Heat Transfer Calculations

#### Parallel Flow

**Hot stream:**

$$\dot{Q}_{hot} = \dot{m}_h \cdot 4.18 \cdot (45.0 - 22.9) = 92.38 \cdot \dot{m}_h \text{ kW}$$

**Cold stream:**

$$\dot{Q}_{cold} = \dot{m}_c \cdot 4.18 \cdot (18.6 - 7.0) = 48.49 \cdot \dot{m}_c \text{ kW}$$

**Flow rate ratio from energy balance:**

$$\frac{\dot{m}_c}{\dot{m}_h} = \frac{92.38}{48.49} = 1.905$$

#### Counter Flow

**Hot stream:**

$$\dot{Q}_{hot} = \dot{m}_h \cdot 4.18 \cdot (45.0 - 23.7) = 89.03 \cdot \dot{m}_h \text{ kW}$$

**Cold stream:**

$$\dot{Q}_{cold} = \dot{m}_c \cdot 4.18 \cdot (28.2 - 11.4) = 70.22 \cdot \dot{m}_c \text{ kW}$$

**Flow rate ratio:**

$$\frac{\dot{m}_c}{\dot{m}_h} = \frac{89.03}{70.22} = 1.268$$

### Effectiveness Analysis

Heat exchanger effectiveness: $\varepsilon = \dot{Q}_{actual} / \dot{Q}_{max}$

**Parallel Flow:**

$$\dot{Q}_{max} = \dot{m}_h \cdot c_p \cdot (T_1 - T_3) = 158.84 \cdot \dot{m}_h \text{ kW}$$

$$\varepsilon_{parallel} = \frac{92.38}{158.84} = 0.582 = 58.2\%$$

**Counter Flow:**

$$\dot{Q}_{max} = \dot{m}_h \cdot c_p \cdot (T_1 - T_3) = 140.45 \cdot \dot{m}_h \text{ kW}$$

$$\varepsilon_{counter} = \frac{89.03}{140.45} = 0.634 = 63.4\%$$

### Performance Comparison

| Configuration | Hot ΔT (°C) | Cold ΔT (°C) | Effectiveness | Flow Ratio |
|---------------|-------------|--------------|---------------|------------|
| Parallel Flow | 22.1 | 11.6 | 58.2% | 1.905 |
| Counter Flow | 21.3 | 16.8 | 63.4% | 1.268 |
| **Improvement** | -3.6% | **+45%** | **+8.9%** | - |

<div style="background-color: #e8f4f8; border-left: 4px solid #0066cc; padding: 1em; margin: 1.5em 0;">
  <strong>Key Result:</strong> Counter flow achieves 45% greater cold stream temperature rise and 8.9% higher effectiveness.
</div>

---

## 6. Entropy Analysis

For steady-state operation with $\Delta s = c_p \cdot \ln(T_{out}/T_{in})$:

### Parallel Flow

Converting to Kelvin: $T_1=318.15$ K, $T_2=296.05$ K, $T_3=280.15$ K, $T_4=291.75$ K

$$\dot{S}_{gen} = \dot{m}_h \cdot c_p \cdot \ln(T_2/T_1) + \dot{m}_c \cdot c_p \cdot \ln(T_4/T_3)$$

$$\dot{S}_{gen} = \dot{m}_h \cdot 4.18 \cdot \ln(0.9306) + 1.905 \cdot \dot{m}_h \cdot 4.18 \cdot \ln(1.0414)$$

$$\dot{S}_{gen} = 0.023 \cdot \dot{m}_h \text{ kW/K}$$

### Counter Flow

Converting to Kelvin: $T_1=318.15$ K, $T_2=296.85$ K, $T_3=284.55$ K, $T_4=301.35$ K

$$\dot{S}_{gen} = \dot{m}_h \cdot c_p \cdot \ln(T_2/T_1) + \dot{m}_c \cdot c_p \cdot \ln(T_4/T_3)$$

$$\dot{S}_{gen} = \dot{m}_h \cdot 4.18 \cdot \ln(0.9330) + 1.268 \cdot \dot{m}_h \cdot 4.18 \cdot \ln(1.0590)$$

$$\dot{S}_{gen} = 0.014 \cdot \dot{m}_h \text{ kW/K}$$

**Result**: Counter flow generates **39% less entropy** (0.014 vs 0.023 kW/K), indicating superior thermodynamic efficiency.

---

## 7. Design Change Analysis

### Configuration: Parallel → Counter Flow

**Performance improvements:**
- Cold outlet temperature: +9.6°C (18.6°C → 28.2°C)
- Effectiveness: +8.9% (58.2% → 63.4%)
- Entropy generation: -39%
- Temperature driving force: More uniform along exchanger length

**Why counter flow is superior:**

Counter flow maintains a larger, more uniform temperature difference between hot and cold streams throughout the exchanger. In parallel flow, both streams approach the same temperature at the outlet, reducing the driving force. In counter flow, the cold outlet can approach the hot inlet temperature, enabling greater heat transfer.

### Other Design Considerations

**Increasing hot reservoir temperature** ($T_1$: 45°C → 60°C):
- Increases heat transfer capacity
- Raises cold outlet temperature
- Larger temperature driving force throughout

**Adjusting flow rates** (increasing $\dot{m}_h$):
- From energy balance: $\dot{Q} = \dot{m}_h \cdot c_p \cdot (T_1-T_2) = \dot{m}_c \cdot c_p \cdot (T_4-T_3)$
- Higher hot flow → smaller hot ΔT → hotter outlet
- Trade-off between flow rate and temperature change

**Restricting cold flow** (decreasing $\dot{m}_c$):
- Requires larger cold ΔT to maintain energy balance
- Risk of excessive outlet temperature (boiling)
- Critical consideration in cooling applications (automotive, reactors)

**Insulation effects:**
- Reduces parasitic heat loss to environment
- Improves effectiveness
- Essential for high-temperature industrial applications

---

## 8. Conclusions

### Key Findings

1. **Counter flow demonstrates superior performance:**
   - 45% greater cold stream temperature rise
   - 8.9% higher effectiveness
   - 39% less entropy generation
   - More uniform temperature driving force

2. **Experimental validation:**
   - Energy balance confirmed: $\dot{Q}_h = \dot{Q}_c$
   - Flow rate ratios: $\dot{m}_c/\dot{m}_h = 1.905$ (parallel), $1.268$ (counter)
   - Assumptions (adiabatic, steady-state) reasonably satisfied

3. **Design insights:**
   - Configuration choice significantly impacts performance
   - Flow rate adjustments enable performance tuning
   - Insulation reduces efficiency losses

---

*ENGRD 2210 Portfolio - Cornell University, Fall 2025*
