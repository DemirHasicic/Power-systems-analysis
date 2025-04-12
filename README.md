# ⚡ Power System DAE Modeling and Simulation

This repository presents the modeling and simulation of a dynamic power system using **differential-algebraic equations (DAEs)**. The study focuses on a simplified electrical network composed of **3 synchronous generators** and **9 buses**, capturing transient system behavior and signal evolution. The work was originally developed as part of a seminar paper at the Faculty of Electrical Engineering, University of Sarajevo.

---

## 🧠 Project Overview

The core objective of this project is to simulate the transient response and dynamic characteristics of an electrical power system by:

- Formulating the system equations as a **set of DAEs**
- Encoding system topology and parameters in a **custom XML-based Model Solver**
- Performing **signal analysis in Python** using the generated simulation outputs

The project provides insight into how large-scale interconnected systems can be represented and analyzed using modern modeling techniques.

---

## 🧩 System Structure

- **3 synchronous generators**
  - Classical model with rotor dynamics and excitation systems
- **9 buses**
  - Interconnecting generators and loads with specified line parameters
- **Differential-algebraic equation formulation**
  - State variables: rotor angles, speeds, voltages
  - Algebraic constraints: network equations, bus admittance

---

## 🛠 Tools & Technologies

- ⚙️ **Custom XML Model Solver**
  - Used to encode system components, node topology, and simulation settings
- 🐍 **Python**
  - Signal post-processing
  - Visualization of generator response, frequency, and angle deviations
- 📊 **Plots**
  - Voltage, current, and angular velocity across the system over time

## 🧩 XML Model Descriptions

The following XML files define differential-algebraic equation (DAE) based models used for power system dynamic simulations. They are structured for compatibility with custom DAE solvers and demonstrate increasing levels of complexity.

---

### `dae_generator_basic.xml`

This model represents a **single synchronous generator connected to an isolated node**. It serves as a foundational template for testing DAE-based solvers and simulation algorithms.

**Features:**
- Full DAE formulation including both differential and algebraic components
- Solved using the **Trapezoidal Integration Method** for improved numerical stability
- Includes the **initial power flow subproblem** to compute steady-state operating conditions
- Models **rotor angle** (`δ`) and **rotor speed** (`ω`) dynamics
- Includes an **automatic voltage regulator (AVR)** and a **simple excitation system**
- Ideal for testing basic stability, rotor angle dynamics, and AVR responses

---

### `dae_generator_extended.xml`

This file extends the basic model into a **more complex generator model embedded in a multi-node power system**.

**Features:**
- Incorporates generator dynamics similar to `dae_generator_basic.xml`, but within a **networked power system**
- Includes **multiple buses**, line admittances, and algebraic constraints representing **nodal power balance**
- Enables simulation of **inter-machine oscillations** and **dynamic interactions** across the grid
- Supports advanced studies including **small-signal stability**, **fault transients**, and **control system effects**
- Suitable for validating solver robustness under **realistic operating conditions**

---

📘 These files are intended for use with a custom DAE simulation engine and can be adapted for larger systems or used to benchmark various numerical integration methods such as trapezoidal rule, backward Euler, or implicit Runge-Kutta.

---
📊 Plotting Scripts
The repository includes several Python scripts for plotting selected variables from the simulation results. These scripts automatically parse the output file generated by the DAE solver and visualize relevant quantities:

Script Name	Description
plotsol2.py	Plots generator rotor angle, AVR input/output signals, and excitation system dynamics.
plotsol3.py	Visualizes active and reactive power outputs, as well as internal generator states such as voltage and flux linkages.
plotsol4.py	Focuses on terminal voltage, internal EMF, field voltage, and rotor speed. Useful for analyzing dynamic stability.
plotsol5.py	Displays multiple internal states of the excitation system and generator electrical variables to study system response in depth.

## 🎓 Academic Context

- **Course**: Power System Modeling and Analysis  
- **Authors**: Demir Hasičić, Jumna Alić
- **Institution**: Faculty of Electrical Engineering, University of Sarajevo  
- **Supervisor**: Prof. Dr. Izudin Džafić 
- **Date**: September 2023

---

## 📌 Outcome

The project successfully demonstrates:

- Construction of a dynamic model using differential-algebraic formulation
- Simulation of realistic multi-generator power systems
- Use of scripting tools (Python) for signal processing and analysis
- Application of academic theory in a custom-built modeling framework
