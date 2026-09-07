# Kit de inicio

*Edición en español (México), traducida de la versión inglesa: el commit 40494f3 y la revisión inglesa del 2026-09-06, que se publica en el mismo commit que esta traducción. La versión en inglés es la canónica.*

Comience aquí: `rollout-guide.md`. Todo lo demás en esta carpeta es lo
que esa guía utiliza.

Plantillas reutilizables y depuradas del modelo operativo descrito en la
tesis. Tómelas, adáptelas y mantenga intactas las reglas de honestidad.
Las plantillas son MIT; la prosa de la guía de implementación, como las
demás obras escritas de este repositorio, es CC BY 4.0. Plantillas
vigentes a la versión 4 de la tesis, 2026-08-02. Comportamientos del
entorno de ejecución (harness) cotejados contra la documentación de
Claude Code: vea el párrafo de verificación del harness en la guía de
implementación para la fecha y la versión.

Contenido.

- `rollout-guide.md`. Instrucciones paso a paso y tres prompts para
  copiar y pegar que levantan los cimientos y su primer espacio de
  trabajo (workspace) en una sola sesión guiada, y después dicen qué
  viene y cuándo.
- `skeleton-template.md`. El marco de nueve partes con el que se
  construye cada workspace. Comience cualquier nuevo
  dominio de trabajo administrado por IA llenando esta plantilla.
- `workspace-loader-template.md`. El delgado archivo cargador bajo
  demanda que hace que un workspace se cargue por sí solo sin inflar el
  contexto siempre activo.
- `intake-command-template.md`. El protocolo de ingesta de artefactos.
  Suelte cualquier archivo, hágale ingeniería inversa, interrogue el
  encuadre y deje tras de sí tanto una instancia como una plantilla
  reutilizable.
- `adversarial-review-protocol.md`. El protocolo de revisión entre
  proveedores, agnóstico al modelo: separación entre autor y auditor, un
  intercambio contenido, rondas en las que cada parte verifica las
  correcciones de la otra y un menú de decisiones que mantiene al humano
  al mando.

Dos conceptos que estas plantillas referencian sin proveer, porque son de
uno por sistema y no de uno por workspace. La capa global siempre cargada
(el delgado archivo raíz de instrucciones) y la bandeja de entrada de
lecciones entre dominios se describen ambas en la tesis, la capa global
en su sección de arquitectura y el enrutamiento de lecciones en su
sección del esqueleto; construya las suyas una vez y todos los workspaces
las comparten.

El alcance, dicho con claridad. Las plantillas, tal como se entregan,
están dirigidas a Claude Code, que proporciona carga de contexto activada
por carpeta, importación de archivos y comandos personalizados (skills,
en el Claude Code actual); portarlas a otro entorno de ejecución
(harness) requiere equivalentes de esas tres capacidades. Y el
esqueleto rige cómo se produce y se verifica el trabajo con IA. No
proporciona modelado de amenazas, clasificación de datos, manejo de
secretos, control de acceso, respuesta a incidentes, pruebas de
respaldos, reglas de retención y eliminación, fronteras contra la
inyección de prompts, reversión de cambios, titularidad de los controles,
vencimiento de excepciones, estándares de evidencia ni aplicación
automatizada de los controles; aporte los suyos o ejecute el sistema
dentro de un entorno que ya los tenga.

Ninguna de estas plantillas contiene nada del repositorio privado más
allá de la estructura. Llénelas con su propia doctrina. El marco es el
regalo; el contenido es suyo.
