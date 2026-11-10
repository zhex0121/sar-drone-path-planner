# Autonomous SAR Drone Path Planner

An advanced, probabilistic spatial path-planning engine designed for autonomous Search and Rescue (SAR) drone operations. This repository features the core algorithm and test suite independently authored for a multi-drone simulation and tasking framework.

## Overview & Architecture

When conducting automated search operations, traditional approaches often waste critical battery life on frequent turnarounds. This module implements an optimized TSP-lite tour-packing algorithm combined with Bayesian belief updates to maximize search efficiency across dynamic probability grids.

### Key Engineering Features

- Multi-Block Tour Packing: Dynamically groups up to $N$ adjacent high-probability search blocks into a single efficient sortie, significantly reducing transit overhead.
- Dynamic Probability & Entropy Fusion: Blends spatial priors (e.g., ISRID statistics, ring priors) with real-time Bayesian belief updates and a time-dependent entropy reduction scaling factor for long-tail search phases.
- Asynchronous Mid-Flight Retasking: Evaluates incoming detection hypotheses or observation feeds on-the-fly, allowing drones to be dynamically retasked to high-priority target zones.
- Rigorous Automated Testing: Includes a dedicated unit test suite (`test_planner.py`) verifying multi-block packing efficiency, fleet fault-tolerance (handling lost drones), and behavioral divergence from baseline strategies.

## Codebase Structure

```
sar-drone-path-planner/
├── src/
│   └── planner.py             # Core SearchPlanner algorithm and dynamic scoring logic
├── tests/
│   └── test_planner.py        # Automated test suite (TSP-lite, coverage, and fault-tolerance)
├── requirements.txt           # Core dependencies (NumPy, Pytest)
└── LICENSE                    # MIT License
```

## Attribution & Context

This module was originally architected and implemented as the core path-planning and tasking engine for the team project lastseen. It has been extracted and refactored into a standalone repository to showcase algorithmic design, spatial optimization, and automated testing in multi-drone search-and-rescue simulations.

## License

This project is open-sourced under the terms of the MIT License.