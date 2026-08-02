# Estudio de trabajos previos - 2026-07-12

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Elaborado bajo las reglas de investigación de este proyecto: búsqueda web en
vivo, cada fuente es una URL que quien investigó vio realmente, y las ideas
tomadas de terceros se acreditan. Hallazgos condensados; la sección de
trabajos previos de la tesis, "Dónde se ubica esto entre lo que ya es
público" ("Where this sits among what is already public"), se deriva de este
archivo.

Nota de método (agregada después de la auditoría externa de la ronda 1; el
alcance se acotó después de la ronda 2). Este es un barrido estructurado y
acotado, no un estudio sistemático ni reproducible: las consultas de búsqueda
originales no se conservaron, de modo que el registro siguiente consiste en
las fuentes revisadas y los juicios emitidos, acotados a esta fecha. Las
búsquedas se ejecutaron el 2026-07-12 mediante búsqueda web general desde
varios ángulos: repositorios públicos de GitHub
que comparten configuraciones de Claude Code y listas curadas tipo "awesome",
artículos de practicantes del tipo "cómo trabajo con IA", y la literatura de
conceptos con nombre (context engineering, LLM-as-judge, modelos de madurez
de IA, rutas doradas, context rot). La selección fue el juicio de quien
investigó sobre los resultados más relevantes por ángulo, no un censo
exhaustivo, y ninguna afirmación negativa de este archivo se extiende más
allá de estas búsquedas en esta fecha. Las etiquetas comparativas como
ampliamente referenciado son impresiones descriptivas de los resultados de
búsqueda, marcadas como juicio donde importan.

## Lo que existe públicamente

- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)
  - un directorio curado de recursos de Claude Code ampliamente referenciado,
  el más grande encontrado en esta búsqueda. Amplitud, sin metodología.
  También el lugar natural para conseguir que esta tesis quede listada.
- [awesome-claude-md](https://github.com/josix/awesome-claude-md) - archivos
  CLAUDE.md ejemplares y plantillas. Enfoque en un solo archivo, sin carga
  por capas.
- [claude-failures](https://github.com/ctoth/claude-failures) - análisis
  post-mortem fechados de incidentes reales de Claude Code con reglas
  preventivas. Evidencia de que el género del fallo honesto se practica
  públicamente; que gana credibilidad es juicio de este autor. Los fallos no
  están integrados en un sistema rector.
- [carls-product-os](https://github.com/carlvellotti/carls-product-os) - el
  sistema operativo de espacio de trabajo (workspace) personal de un gerente
  de producto. Arquitectura limpia, sin verificación, medición ni
  mantenimiento.
- [lifeos-template](https://github.com/seandavi/lifeos-template) - el vecino
  más cercano en mantenimiento: una habilidad /audit que califica la bóveda,
  revisiones de decisiones, reescrituras trimestrales forzadas. Alcance de
  vida personal, sin capas de verificación ni modelo de madurez.
- [life-system](https://github.com/davidhariri/life-system) - CLAUDE.md como
  "constitución", detección de deriva. Sin compuertas de verificación ni de
  ratificación.
- [Andrews, Claude Code for Non-Coders](https://medium.com/@k3vin.andrews1/claude-code-for-non-coders-by-a-non-coder-a7a67fcce236)
  - el sistema de dos roles de un abogado con etiquetas de afirmación
  PRIMARY/SECONDARY/INFERENCE/UNVERIFIED; la verificación planteada como
  deber profesional. El par más cercano al planteamiento de verificación por
  capas. Sin medición ni mantenimiento de doctrina.
- [Harper Reed](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/)
  y [Simon Willison](https://simonwillison.net/2025/Feb/21/my-llm-codegen-workflow-atm/)
  - ejemplos ampliamente citados del género de credibilidad "cómo trabajo
  con IA" (juicio del autor). Flujos de trabajo de generación de código, no
  modelos operativos.

## Conceptos con nombre por citar

- Context engineering (ingeniería de contexto) - [el ensayo de Anthropic](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  ("smallest possible set of high-signal tokens", el conjunto más pequeño
  posible de tokens de alta señal); el diseño por capas de raíz y cargador es
  una aplicación directa. También [las mejores prácticas de Claude Code](https://code.claude.com/docs/en/best-practices).
- Context rot (degradación del contexto) - [ahora un problema con nombre entre practicantes](https://www.mindstudio.ai/blog/what-is-context-rot-claude-code);
  gancho para la historia del mantenimiento de doctrina.
- LLM-as-judge (el LLM como juez) en evaluación por capas - [Braintrust](https://www.braintrust.dev/articles/what-is-llm-as-a-judge),
  [DeepEval](https://deepeval.com/blog/llm-as-a-judge).
- Defensa en profundidad para salidas de IA - literatura de guardrails
  (barreras de seguridad) ([Patronus](https://www.patronus.ai/ai-reliability/ai-guardrails)),
  planteada para productos, no para la práctica personal.
- Modelos de madurez de IA - [MITRE](https://aimaturitymodel.mitre.org/) y
  [Microsoft](https://learn.microsoft.com/en-us/agents/adoption-maturity-model/),
  ambos a nivel organizacional. Nadie de quienes encontramos califica su propia
  práctica individual.
- Rutas doradas (golden paths) - [platformengineering.org](https://platformengineering.org/blog/what-are-golden-paths-a-guide-to-streamlining-developer-workflows),
  [Red Hat](https://www.redhat.com/en/topics/platform-engineering/golden-paths);
  el esqueleto es una ruta dorada para espacios de trabajo.

## La brecha (no encontrada en esta búsqueda; acotada según la nota de método)

Cada pieza del sistema tiene un vecino cercano en alguna parte, pero ninguna
fuente encontrada cierra el ciclo en un solo sistema de practicante: doctrina
mantenida contra la degradación, un modelo de madurez y un tablero de
calificación mensual aplicados a una práctica individual, modos de falla
retroalimentados a las reglas rectoras, y un modelo formal de autoridad
humana (validar antes de construir, compuertas de ratificación, separación
entre autor y auditor). El movimiento del tablero de calificación individual
no se encontró en ninguna fuente revisada por esta búsqueda. El planteamiento
de líder de seguridad (defensa en profundidad y evaluación honesta de
controles aplicadas a las salidas de IA propias) tampoco se encontró en las
fuentes revisadas. Ambas afirmaciones negativas están acotadas a las
búsquedas descritas en la nota de método, con fecha 2026-07-12.
