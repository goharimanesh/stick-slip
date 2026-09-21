# Drillstring Stick-Slip Control

Real-time browser simulation of stick-slip vibrations in oilwell drillstrings with PI/PID rotary-table control, calibrated ROP model, and 3D visualization.

---

## Overview

This repository contains the simulation code accompanying the paper:

> **H. Ghantioos, M. Goharimanesh, and A. Akbari**, *"PI/PID Feedback Control of Stick-Slip Vibrations: ROP Recovery in Rotary Drilling ."*

The code implements a **two-degree-of-freedom (2-DOF) lumped-parameter model** of a rotary drilling system, coupled with a **non-regularized dry-friction bit-rock interaction law**, to reproduce and quantify stick-slip behavior at the drill bit. Both **PI and PID feedback controllers** are designed and tuned via grid-search optimization to regulate the rotary-table speed and suppress stick-slip.

A field-data-calibrated empirical ROP model (derived from a real mud-logging record spanning 20 m to 2200 m measured depth) is used to translate simulated bit-speed histories into physically meaningful ROP predictions.

---

## Features

- **2-DOF torsional drillstring model** with equivalent lumped stiffness and damping
- **Non-regularized three-phase dry-friction law** (stick / transition / slip) reproducing velocity-weakening behavior
- **Field-data-calibrated ROP model** (outlier-robust regression on 3527 valid mud-logging points)
- **PI and PID controllers** tuned by exhaustive grid search on the mean of √|ω_b|
- **Interactive browser-based simulator** with:
  - Real-time playback and timeline scrubbing
  - 3D wellbore, drillstring, and drill-bit animation (Three.js)
  - Live plots of bit speed, bit angle, reactive torque, and ROP (Plotly)
  - Side-by-side comparison of open-loop vs. PI-controlled response
- **MATLAB reference implementation** using `ode15s` (stiff ODE solver)

---

## Quick Start

### Browser Simulator (no installation required)

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/drillstring-stick-slip-control.git
