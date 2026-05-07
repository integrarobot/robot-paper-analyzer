# Capability Rubric

Use this rubric to turn a robotics research source into a capability-level reading for students of physical AI.

## Capability Layers

Classify the project into one or more layers:

- **Data engine**: creates, collects, cleans, retargets, labels, augments, or benchmarks robot-relevant data.
- **Representation**: builds an intermediate form such as keypoints, motion priors, latent actions, voxel grids, trajectories, affordances, tokens, world models, or spatial memory.
- **Perception**: improves how the robot sees, localizes, tracks objects, understands scenes, estimates pose, or handles sensor noise.
- **Reasoning and planning**: turns goals, language, spatial constraints, affordances, or task context into action plans.
- **Control**: turns commands or references into stable physical motion, often through RL, imitation, MPC, diffusion, or whole-body control.
- **Manipulation**: improves grasping, pushing, carrying, opening, tool use, bimanual work, loco-manipulation, or dexterous interaction.
- **Locomotion and navigation**: improves walking, local navigation, obstacle traversal, balance, terrain handling, or motion style.
- **Contact and compliance**: improves force, stiffness, safety, human contact, deformable interaction, payloads, wiping, pushing, or collaborative handling.
- **Sim-to-real**: improves transfer from simulation to real hardware through randomization, system identification, teacher-student learning, DAgger, calibration, or real-to-sim alignment.
- **Tooling and infrastructure**: provides simulators, frameworks, SDKs, deployment pipelines, evaluation harnesses, retargeting tools, or training libraries.
- **Evaluation and benchmark**: provides tasks, metrics, datasets, cloud evaluation, reproducibility tests, or failure analysis.

## Relevance Levels

- **High relevance**: advances a bottleneck directly tied to useful real-world robots and includes credible evidence such as real hardware, released code/data, strong evaluation, or clear deployment path.
- **Medium relevance**: advances an important capability but evidence is limited, scope is narrow, code/data are incomplete, or the path to deployment is indirect.
- **Low relevance**: interesting technically but weakly connected to practical robots, only a polished demo, missing evidence, or mostly speculative.
- **Watchlist**: early but strategically important because it points to a likely direction: world models, VLA, scalable robot data, generalist control, compliance, or sim-to-real infrastructure.

## Maturity Levels

Use one:

1. **Idea / concept**: mostly claim, architecture, or early examples.
2. **Simulation proof**: works in simulation, no convincing real-robot evidence.
3. **Hardware demo**: runs on a real robot, usually controlled setting.
4. **Reproducible research artifact**: code, data, configs, or checkpoints allow others to inspect or build on it.
5. **Capability prototype**: repeated success across tasks, objects, scenes, or users; limitations are documented.
6. **Deployment candidate**: robust enough to be evaluated in operational pilots with safety, integration, monitoring, and human fallback.

## Evidence Checklist

Look for:

- linked paper or technical report;
- GitHub repo;
- install and inference instructions;
- training code;
- pretrained checkpoints;
- dataset or benchmark;
- real robot videos;
- robot model and hardware details;
- simulator details;
- success rates;
- ablation studies;
- failure cases;
- comparison against baselines;
- sim-to-real procedure;
- license and reproducibility constraints.

## Real-World Utility Questions

Ask:

1. What real task gets easier because of this work?
2. Does it reduce a known bottleneck: data, control, perception, contact, cost, safety, reliability, integration, or generalization?
3. Does it work only in a lab, or can it tolerate variation in objects, scenes, lighting, people, timing, forces, and failures?
4. Does it require expensive infrastructure such as MoCap, dozens of GPUs, special sensors, or expert teleoperators?
5. Is the output a deployable skill, a training ingredient, an evaluation method, or infrastructure?
6. Which domain is most plausible first: factory, warehouse, home, hotel, restaurant, hospital, agriculture, construction, inspection, mobility, education, or research lab?
7. What would have to happen next before a company could use it?

## Common Interpretive Patterns

### Human Behavior To Robot Skill

If a project learns from video, MoCap, teleoperation, or robot-free demonstrations, explain the translation chain:

human action -> structured representation -> robot-compatible motion -> training objective -> real robot behavior.

Main risk: the human body, environment, and task context may not transfer cleanly to the robot.

### Simulation To Real Robot

If a project trains in simulation, explain:

simulation design -> randomization/calibration -> policy training -> transfer -> real-world validation.

Main risk: visuals, contact physics, latency, friction, compliance, and unmodeled states can break transfer.

### Foundation Model To Robot Action

If a project uses VLA, world models, or embodied foundation models, explain the split:

high-level understanding/planning is not the same as low-level physical control.

Main risk: language/task generalization may not survive contact, timing, and safety constraints.

### Motion Tracking To Useful Task

If a project tracks motions, ask whether it only follows references or also chooses actions to achieve task outcomes.

Main risk: beautiful motion is not the same as task success.

### Compliance And Contact

If a project controls force or stiffness, connect it to usefulness:

real-world robots must touch objects and people safely while still applying enough force to get work done.

Main risk: contact-rich tasks may be fragile across object weights, materials, friction, and human behavior.

## Final Tone

Use course-friendly Spanish:

- clear but not simplistic;
- concrete examples;
- no unnecessary math unless it clarifies the contribution;
- define terms like sim-to-real, retargeting, VLA, world model, diffusion policy, compliance, or whole-body control in one sentence when used;
- end with practical judgment, not hype.
