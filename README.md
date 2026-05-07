# Robot Paper Analyzer

Skill de Codex para analizar investigaciones de robótica desde el punto de vista de la IA Física.

Está pensada para alumnos del curso de Integrarobot. Cuando se le pasa una URL de GitHub, arXiv, una página de proyecto, un dataset o una demo técnica, ayuda a responder:

- si la investigación es relevante;
- qué capacidad robótica aporta;
- cómo podría aplicarse a robots reales;
- qué evidencia existe;
- qué limitaciones mantiene;
- si acerca a robots útiles en industria, hogares, servicios, logística, salud, agricultura u otros contextos.

## Instalación En Codex

Desde Codex, pide:

```text
Instala la skill desde https://github.com/TU-USUARIO/robot-paper-analyzer/tree/main/robot-paper-analyzer
```

Sustituye `TU-USUARIO` por el usuario u organización de GitHub donde publiques este repositorio.

Después de instalarla, reinicia Codex para que aparezca entre las skills disponibles.

## Uso

Ejemplo:

```text
Usa $robot-paper-analyzer para analizar este proyecto:
https://github.com/DAVIAN-Robotics/PHUMA
```

La skill debe producir una lectura orientada a alumnos, no un resumen académico genérico. El objetivo es entender si la investigación aporta una capacidad útil para robots reales y qué tendría que pasar para que esa capacidad llegue a aplicaciones prácticas.

## Estructura

```text
robot-paper-analyzer/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── capability-rubric.md
```

## Licencia

Puedes adaptar este material para el curso de Integrarobot. Si publicas una versión pública, añade la licencia que prefieras para el repositorio.
