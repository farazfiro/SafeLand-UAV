# SafeLand-UAV

<p align="center">
  <img src="assets/safeland-cover.png" alt="SafeLand-UAV Cover" width="1000"/>
</p>

### Uncertainty-Aware Visual Perception for Autonomous UAV Landing

> **Status:** Work in Progress 🚧  
> Simulation-first research project. No physical UAV hardware is required.

SafeLand-UAV is a simulation-based autonomous landing system for UAVs that combines
computer vision, uncertainty estimation, and flight-control integration. The project
investigates whether **predictive uncertainty can reduce unsafe landing decisions under
visual distribution shifts** such as low illumination, image noise, blur, occlusion,
and environmental disturbances.

## Why this project?

Modern autonomous systems should not only make predictions — they should also estimate
**when those predictions are unreliable**. SafeLand-UAV explores this problem in the
context of visual autonomous landing.

The long-term goal is an end-to-end pipeline:

```text
Simulated UAV + RGB Camera
          ↓
Visual Landing-Target Detection
          ↓
Predictive Uncertainty Estimation
          ↓
Landing Safety / Decision Logic
          ↓
PX4 Flight Controller
          ↓
Autonomous Landing
```

## Research Question

**Can predictive uncertainty be used to reduce unsafe autonomous landing decisions
under visual distribution shifts?**

## Planned System Architecture

- **Simulation:** PX4 SITL + Gazebo
- **Perception:** PyTorch-based visual target detector
- **Computer Vision:** OpenCV
- **Uncertainty:** Deep Ensembles and/or Monte-Carlo Dropout
- **Robotics integration:** ROS 2 (planned after the initial simulator baseline)
- **Evaluation:** automated scenario generation and statistical benchmarking
- **Development:** Python, Git/GitHub

## Planned Evaluation Scenarios

The perception and landing system will be evaluated under controlled perturbations:

- varying illumination
- image noise and blur
- partial target occlusion
- camera pose variation
- wind disturbances
- unseen landing configurations

Primary metrics will include:

- target-detection accuracy
- landing-position error
- landing success rate
- unsafe landing rate
- uncertainty calibration
- inference/runtime performance

## Baselines

The planned comparison includes:

1. Classical vision baseline
2. Neural visual detector
3. Neural detector + predictive uncertainty
4. Uncertainty-aware landing decision logic

## Roadmap

- [ ] **Phase 0 — Project & environment setup**
- [ ] **Phase 1 — PX4/Gazebo UAV simulation baseline**
- [ ] **Phase 2 — RGB camera and landing-target dataset generation**
- [ ] **Phase 3 — Classical computer-vision baseline**
- [ ] **Phase 4 — PyTorch visual detector**
- [ ] **Phase 5 — Uncertainty estimation**
- [ ] **Phase 6 — Autonomous landing decision/control integration**
- [ ] **Phase 7 — Robustness benchmark and ablation study**
- [ ] **Phase 8 — Documentation, demo video, and technical report**

## Repository Structure

```text
SafeLand-UAV/
├── assets/                 # README figures and demo media
├── configs/                # experiment and simulation configuration
├── docs/                   # architecture and technical notes
├── src/
│   └── safeland/
│       └── __init__.py
├── tests/
├── .gitignore
├── README.md
└── ROADMAP.md
```

## Current Development Target

The first milestone is intentionally small:

> **Run a simulated UAV in PX4/Gazebo and establish a reproducible baseline before
> introducing machine learning.**

This keeps the project simulation-first and ensures that later ML results can be
compared against a stable robotics baseline.

## Reproducibility

The project will be developed so that simulation scenarios, model configurations,
and evaluation runs can be reproduced from version-controlled configuration files.

## Author

**Faraz Firouzbakht**  
M.Sc. Mechanical Engineering — Robotics & AI  
Karlsruhe Institute of Technology (KIT)

GitHub: https://github.com/farazfiro
