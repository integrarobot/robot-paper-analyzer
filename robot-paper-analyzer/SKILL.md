---
name: robot-paper-analyzer
description: Analyze robotics research URLs, project pages, GitHub repositories, arXiv papers, lab demos, datasets, benchmarks, and engineering releases for students of Integrarobot's physical AI course. Use when Codex receives a robotics research link and must explain whether the work is relevant, what practical capability it contributes, how it could be applied to real robots, what evidence supports it, and whether it moves robots closer to useful deployment in industry, homes, services, logistics, healthcare, agriculture, construction, or other real-world settings.
---

# Robot Paper Analyzer

## Purpose

Turn a robotics research URL into a clear capability reading for physical-AI students. Explain the work as a step toward useful robots, not as a generic academic summary.

The output should help a non-specialist but motivated student answer:

- Is this research relevant?
- What robot capability does it improve?
- How could it be applied to real robots?
- What evidence shows that it works?
- What still blocks real-world usefulness?
- Why should Integrarobot track it?

## Required Workflow

1. Open the supplied URL.
2. If it is a project page, identify and open the linked paper, GitHub repo, dataset, model card, documentation, or video when those links are needed to verify claims.
3. If the page is JavaScript-heavy or sparse, search for the title on arXiv, GitHub, Hugging Face, the lab page, or the project PDF.
4. Extract only claims grounded in the source. Mark interpretations as inference.
5. Classify the contribution using `references/capability-rubric.md`.
6. Answer in Spanish unless the user asks otherwise.
7. Keep the result useful for course learning: define technical terms briefly and connect them to robot utility.

When current factual accuracy matters, browse or use the linked primary sources. Prefer primary sources over commentary: project page, paper, repo, dataset, model card, official docs, lab post.

## Output Shape

Use this structure by default:

```markdown
## Veredicto rapido

[1-3 sentences: relevant/not relevant, why, and what capability it advances.]

## Que aporta

- Capacidad:
- Capa del stack:
- Robot/cuerpo objetivo:
- Fuente de aprendizaje:
- Metodo central:

## Como podria aplicarse

[Explain practical path to robots in industry, homes, services, logistics, healthcare, etc. Be concrete.]

## Evidencia disponible

- Hardware real:
- Simulacion:
- Codigo/modelos/datos:
- Metricas o demos:
- Limitaciones de evidencia:

## Madurez

[Use one maturity level from the rubric and justify.]

## Lectura para alumnos

[Plain-language teaching explanation: why this matters for physical AI.]

## Preguntas criticas

- [Question 1]
- [Question 2]
- [Question 3]
```

For broad reviews across many links, group projects by capability layer instead of repeating the full template for every item.

## Analysis Rules

- Do not equate a polished demo with deployable capability.
- Do not assume Unitree relevance just because a link appears in a Unitree-related list; verify the robot embodiment.
- Separate "the paper claims", "the released repo contains", and "this implies for Integrarobot".
- Identify the learning source: human video, MoCap, teleoperation, robot-free demos, simulation, generated video, real robot data, dataset, or mixed data.
- Identify whether the work improves high-level reasoning, perception, planning, control, manipulation, locomotion, contact, compliance, sim-to-real, data collection, evaluation, or tooling.
- Pay special attention to evidence of real-world transfer: real robot videos, success rates, ablations, released code, checkpoints, datasets, hardware details, failure cases, and reproducibility.
- When a project has no code or only "coming soon", say so plainly.
- When a project is useful mainly as infrastructure or dataset, explain that its value is enabling later capabilities rather than directly performing a task.

## Course Framing

Frame every analysis around physical AI:

> A robot becomes useful when perception, reasoning, planning, control, embodiment, safety, reliability, and integration line up for a real task.

Use the research to teach one of these lessons:

- how robots learn from human behavior;
- how simulation becomes training ground;
- how VLA or world models connect understanding to action;
- why whole-body control matters for humanoids;
- why contact and compliance are central to real work;
- why sim-to-real is hard;
- how to distinguish demo, prototype, capability, and deployment.

## Repository Or GitHub-Specific Checks

When the URL is a GitHub repo:

- Read the README first.
- Check folders for training, inference, deployment, environments, datasets, configs, docs, checkpoints, and examples.
- Check whether install instructions and examples are realistic.
- Distinguish released implementation from paper claims.
- Mention supported robots, simulators, dependencies, license, and whether pretrained assets are available.
- If the repo only supports simulation or only part of the paper, make that central to the answer.

## References

Read `references/capability-rubric.md` when classifying relevance, capability layer, maturity, or real-world utility.
