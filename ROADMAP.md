# SafeLand-UAV — Development Roadmap

## Phase 0 — Repository and environment
- Create public GitHub repository.
- Establish Python environment.
- Define code style, configuration structure, and experiment conventions.
- Document supported development environment.

**Exit criterion:** repository can be cloned and the base environment can be recreated.

## Phase 1 — Simulation baseline
- Install and validate PX4 SITL.
- Install and validate Gazebo.
- Launch a simulated UAV.
- Run one deterministic takeoff/hover/landing sequence.

**Exit criterion:** repeatable baseline flight with logged state data.

## Phase 2 — Camera and synthetic data
- Add downward-facing RGB camera.
- Create a simple landing target.
- Randomize target position, camera pose, and illumination.
- Export images plus automatic simulator-derived ground truth.

**Exit criterion:** reproducible synthetic dataset generator.

## Phase 3 — Classical vision baseline
- Detect target with a non-neural approach.
- Measure localization error under nominal conditions.
- Establish failure modes under blur/noise/light changes.

**Exit criterion:** quantitative baseline.

## Phase 4 — Learned perception
- Fine-tune a lightweight pretrained vision model.
- Compare with the classical baseline.
- Track training/evaluation configuration.

**Exit criterion:** learned detector evaluated on held-out scenarios.

## Phase 5 — Predictive uncertainty
- Implement Deep Ensemble and/or MC Dropout.
- Evaluate calibration and error-vs-uncertainty relationship.
- Define a confidence/uncertainty rejection policy.

**Exit criterion:** uncertainty correlates meaningfully with perception error.

## Phase 6 — Landing integration
- Convert visual target estimate into landing guidance.
- Add uncertainty-aware hold/reacquire logic.
- Integrate with PX4 control interface.

**Exit criterion:** autonomous simulated landing in nominal scenarios.

## Phase 7 — Robustness benchmark
Evaluate across:
- illumination
- blur/noise
- occlusion
- wind
- initial pose
- unseen target configurations

Compare:
1. classical vision
2. neural detector
3. neural detector + uncertainty
4. uncertainty-aware landing policy

**Exit criterion:** statistically meaningful benchmark with multiple runs per scenario.

## Phase 8 — Portfolio release
- Clean README.
- Architecture diagram.
- Demo GIF/video.
- Results tables.
- Ablation study.
- Technical report.
- Reproduction instructions.

**Exit criterion:** repository is recruiter/researcher ready.
