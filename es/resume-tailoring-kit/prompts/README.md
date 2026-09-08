# Kit de adaptación de currículum - README (manual de operación)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)

## Qué es esto

Una biblioteca modular de prompts para adaptar su currículum a puestos objetivo específicos. Construida para hacer cumplir el alcance honesto, las afirmaciones respaldadas por evidencia, la alineación entre documentos, la disciplina de nivelación, la alineación continua del estado, la adaptación del encuadre según el puesto y la limpieza de la salida.

Funciona para cualquier persona en búsqueda de empleo, en cualquier campo. Usted pega estos prompts en un chat de IA común (Claude, ChatGPT o similar), sin git, sin software especial, sin preparación previa. Algunos ejemplos trabajados en los módulos usan puestos de ciberseguridad; reconstruya las listas de ejemplo para su propio campo.

## Alias del nombre

- **Kit de adaptación de currículum** (formal, documentación; en inglés, Resume Tailoring Kit)
- **Pipeline de adaptación** (operativo, flujo de módulos; en inglés, Tailoring Pipeline)
- **Generador de currículum** (abreviado, referencia rápida; en inglés, Resume Generator)

Cualquiera de estos nombres, en español o en inglés, activa el sistema.

## Estructura de carpetas del kit

Configúrela en cualquier lugar de su computadora:

```
resume-tailoring-kit/
  prompts/     - estos módulos más los documentos de referencia (este README vive aquí)
  templates/   - fact_registry_template.json, career_thesis_template.md
  my-data/     - SUS copias privadas (registro de hechos, notas de sesión).
                 Mantenga esta carpeta FUERA de cualquier ubicación pública. Nunca la comparta.
  drafts/      - construcciones en curso, una subcarpeta por puesto objetivo: drafts/[nombre-del-puesto]/
  final/       - paquetes terminados, una subcarpeta por puesto objetivo: final/[nombre-del-puesto]/
```

## Arquitectura

```
00_orchestrator - secuenciador maestro
  Paso 0:   Lectura de base (primero prompts/README.md, este manual de operación,
            y luego sus archivos de my-data: registro de hechos, tesis de carrera y,
            si los lleva, la Outcome Ledger (bitácora de resultados) y la banda de portafolio; principios;
            mapa de equivalencia semántica)
  Paso 0.5: Reconciliación al inicio de sesión + verificación de salud del espacio de trabajo (workspace)
  Paso 1:   Parámetros de la ejecución (el modo de construcción NO se elige aquí; la compuerta lo propone)
  Paso 2a:  STRATEGY GATE (compuerta de estrategia): después del Módulo 13, UNA tarjeta de decisión por puesto objetivo:
            nivel (A/B/C) | banda de portafolio (green (verde) 1-3 / yellow (amarilla) 4-6 / red (roja) 7+) |
            modo propuesto FULL/FAST/LIGHT/NO-BUILD (completo/rápido/ligero/sin construcción) | ruta por la red de contactos (el Módulo 14
            corre DENTRO de la compuerta) | estado del paquete de preparación | SINGLE timebox (límite de tiempo único).
            Usted toma UNA decisión. En amarillo, FAST/LIGHT/preparación es el
            valor por defecto; FULL requiere su decisión explícita más una razón. Los valores por defecto
            nunca bloquean; usted los anula con libertad.
            (Las bandas de portafolio son OPCIONALES; se vuelven útiles cuando usted
            maneja varias postulaciones a la vez.)
  Pasos 2-6: Secuencia del modo, ramificación, cierre (tarjeta + fila de la Outcome Ledger registradas)
  Paso 7:   Cierre de sesión mediante el Módulo 12, que termina guardando sus archivos
            actualizados. Si usa git, haga commit al cierre (opcional).

Modos de construcción (salida de la Strategy Gate; usted decide):
  FULL   - la secuencia completa de abajo
  FAST   - currículum donante del carril + delta de la descripción del puesto (JD) + UNA pasada adversarial en ambas direcciones +
           verificación de hechos (nunca se omite) + control de calidad completo + reclutador + sistema de seguimiento de candidatos (ATS) + pasada
           dirigida de riesgo del gerente de contratación (HM) (incondicional); calificador opcional, lo primero que se recorta
  LIGHT  - artefacto existente de carril/biblioteca tal cual + higiene de datos de contacto/control de calidad únicamente;
           CUALQUIER cambio de contenido lo convierte en FAST
  NO-BUILD - sin construcción nueva; más acotado que DON'T PURSUE (no perseguir), nunca cancela la persecución del puesto objetivo

Detalle del pipeline (modo FULL):
  01_intake_and_matrix        De la JD a la matriz de requisitos + framing_delta_report
  13_target_qualification     GATING CHECKPOINT (punto de control que condiciona el resto): clasifica contra su tesis
                              de carrera; la decisión perseguir / no perseguir condiciona el
                              resto de la ejecución (DON'T PURSUE o HOLD (en espera) la termina aquí)
  STRATEGY GATE (Paso 2a)     La única tarjeta de decisión; el Módulo 14 dentro de ella
                              (ruta completa para nivel A, ruta rápida en los demás casos)
  02_rubric_score (base)      Calificación de línea base
  03_proactive_interrogation  Sacar a la luz experiencia no documentada (si la calificación < 75%
                              o usted lo solicita)
  09_company_research         Contexto de la empresa (DEFAULT ON, activado por defecto, para puestos objetivo serios)
  04_content_build            PRINT (versión para impresión) + ATS en una sola pasada
  07_fact_check               Auditoría antialucinación
  08_cover_letter_build       Carta de presentación (vea COLD PORTAL MODE, modo de portal en frío, en el Módulo 08)
  05_cross_document_alignment Verificación de consistencia
  06_qa_gate                  Batería de control de calidad + panel de personas lectoras
  02_rubric_score (final)     Calificación después de la adaptación
  11_output_packaging         final/[nombre-del-puesto]/ + HANDOFF_MANIFEST.md
  10_interview_prep           (Normalmente en sesión aparte, después del envío)

  12_session_closeout         Corre AL FINAL o de forma quirúrgica en cualquier hito;
                              termina guardando sus archivos actualizados
```

## Por qué es modular

Cada pasada requiere un lente mental distinto:
- **Ruta por la red de contactos (Módulo 14)**: investigación preliminar y estrategia de relaciones
- **Calificación del puesto objetivo (Módulo 13)**: decisión estratégica bajo su tesis de carrera
- **Ingesta y matriz (Módulo 01)**: descomposición estructurada de la JD + detección de framing_delta (delta de encuadre)
- **Calificación por rúbrica (Módulo 02)**: analítica (números, ponderaciones)
- **Interrogatorio (Módulo 03)**: conversacional (indagación)
- **Construcción del contenido (Módulo 04)**: creativa con restricciones (redacción de viñetas siguiendo reglas)
- **Control de calidad (Módulo 06)**: mecánica (lista de verificación) más el panel de personas lectoras
- **Cierre (Módulo 12)**: reconciliación (alineación + guardado de sus archivos)

Cada módulo está enfocado. El orquestador los secuencia; los módulos pueden invocarse solos para repeticiones quirúrgicas.

## Biblioteca de módulos (15 módulos)

Ubicación: `prompts/`

| Módulo | Versión | Propósito |
|---|---|---|
| `00_orchestrator` | v1.0 | Secuenciador maestro; reconciliación del Paso 0.5; el 13 condiciona la ejecución; Strategy Gate en el Paso 2a (una sola tarjeta de decisión, el Módulo 14 dentro); termina guardando sus archivos |
| `01_intake_and_matrix` | v1.0 | De la JD a la matriz de requisitos + framing_delta_report (informe de delta de encuadre); señala el riesgo de eliminación por título universitario |
| `02_rubric_score` | v1.0 | Motor de calificación; reporte de palabras clave literales exactas frente a sinónimos; verificación literal de las MUST-HAVE (imprescindibles) |
| `03_proactive_interrogation` | v1.0 | Preguntas y respuestas para cerrar brechas; recopilación de datos cuantitativos; transcripción obligatoria |
| `04_content_build` | v1.0 | Construcción dual PRINT + ATS; estándar de 2 páginas; ruta FAST con currículum donante; limpieza de caracteres al construir |
| `05_cross_document_alignment` | v1.0 | Coherencia entre el currículum, la carta de presentación y ATS; verificación completa del encuadre bloqueado |
| `06_qa_gate` | v1.0 | Batería de control de calidad, incluida la lista blanca de encabezados definida por script; panel FULL = reclutador/ATS/HM; panel FAST = reclutador/ATS/pasada dirigida de riesgo del HM (incondicional); verificación de voz humana |
| `07_fact_check` | v1.0 | Auditoría antialucinación; rastrea cada afirmación hasta su registro de hechos |
| `08_cover_letter_build` | v1.0 | Estructura de 4 secciones; COLD PORTAL MODE; reglas más estrictas para brechas de credenciales; cero dos puntos en la prosa |
| `09_company_research` | v1.0 | Contexto de la empresa; DEFAULT ON para puestos objetivo serios |
| `10_interview_prep` | v1.0 | Guiones de defensa por puesto objetivo; nota de coherencia para postulaciones internas |
| `11_output_packaging` | v1.0 | Destino final/; HANDOFF_MANIFEST.md; versiones renderizadas en PDF; nombres de archivo para el envío; metadatos del documento |
| `12_session_closeout` | v1.0 | Lista de verificación de cierre; verificación de salud; revalidación periódica de la doctrina (opcional) |
| `13_target_qualification` | v1.0 | Clasifica contra su tesis de carrera; lee el puesto actual desde el registro |
| `14_network_pathway` | v1.0 | Corre dentro de la Strategy Gate; ruta warm (cálida)/hybrid (híbrida)/cold (fría) + movimiento de visibilidad auditable |

Documentos de referencia (misma ubicación):

| Archivo | Versión | Propósito |
|---|---|---|
| `README.md` | v1.0 | Este manual de operación |
| `principles.md` | v1.0 | 15 principios permanentes, distribuidos 7/6/2 entre los tres niveles |
| `semantic_equivalence_map.md` | v1.0 | Grupos de sinónimos + etiquetas [RECOGNITION-ONLY] (solo reconocimiento) |
| `ats_upload_notes.md` | v1.0 | Particularidades por portal; KNOCKOUT PLAYBOOK (guía de preguntas eliminatorias); campos de educación; árbol de decisión ATS frente a PRINT |

## Antes de su primera ejecución

1. Copie `templates/fact_registry_template.json` a `my-data/fact_registry.json` y complételo. Es la base de evidencia a la que toda afirmación debe rastrearse. Manténgalo privado.
2. Copie `templates/career_thesis_template.md` a `my-data/` y defina su propia tesis de carrera (vea abajo).
3. Opcionalmente, inicie `my-data/lessons_learned.md` para registrar patrones reutilizables entre sesiones.

## Cómo usarlo

**Puesto objetivo nuevo (cualquier prioridad):**
Ejecute `00_orchestrator`. Pegue el módulo en un chat de IA nuevo y asegúrese de que su registro de hechos (my-data/fact_registry.json) esté pegado o adjunto en el chat. Después de que el Módulo 13 clasifica, la STRATEGY GATE emite una tarjeta de decisión: nivel, banda de portafolio, modo de construcción propuesto, ruta por la red de contactos (el Módulo 14 corre dentro de la compuerta; una ruta cálida puede pausar el pipeline en espera de la respuesta a la presentación cálida y SUSPENDE el límite de tiempo), estado del paquete de preparación, un solo límite de tiempo. Usted toma una decisión sobre la tarjeta; el modo elegido se ejecuta. Las postulaciones en frío para la ruta de liderazgo sénior obtienen un movimiento de visibilidad registrado o un obstáculo identificado. El Módulo 09 permanece ON para los puestos objetivo serios.

**Puesto objetivo nuevo, exploratorio:**
Omita el Módulo 14. Pegue `00_orchestrator` en un chat nuevo. Pegue la JD. Ejecute. El Módulo 13 clasificará el puesto objetivo después de la ingesta; un resultado DON'T PURSUE o HOLD termina la ejecución antes de invertir cualquier esfuerzo de construcción.

**Quirúrgico (un solo módulo):**
Pegue solo el módulo que necesita. Ejemplos:
- `06_qa_gate` para revisar la calidad de un borrador existente
- `13_target_qualification` para evaluar el ajuste antes de comprometer esfuerzo de adaptación
- `14_network_pathway` para revisar rutas de presentación cálida hacia un puesto objetivo
- `12_session_closeout` para cerrar a mitad de sesión después de un hito

**Frases detonantes del cierre:**
- "¿ya terminamos con X?" | "¿podemos seguir?" | "borrón y cuenta nueva" | "cerremos esto" | "concluyamos"

**Frases detonantes de la ruta por la red de contactos:**
- "¿A quién conozco ahí?" | "Revisión de mi red para este puesto" | "¿hay rutas de presentación cálida?"

## Guardar su trabajo (fuente de verdad)

La carpeta del kit en su computadora es la fuente de verdad.

- **Sus archivos de datos** viven en `my-data/`: `fact_registry.json` (obligatorio) y `lessons_learned.md` (opcional). Al cierre, el Módulo 12 guía al usuario para actualizarlos. Mantenga `my-data/` fuera de cualquier ubicación pública.
- **Guardar sus archivos actualizados al cierre constituye el registro perdurable.** Ninguna sesión que entregue un paquete o cambie sus reglas permanentes está cerrada hasta que los archivos se guardan. Si usa git, haga commit al cierre (opcional).
- **Los entregables** salen a `final/[nombre-del-puesto]/` mediante el Módulo 11, cada paquete con su `HANDOFF_MANIFEST.md` (metadatos del puesto objetivo, inventario de archivos con uso ATS frente a PRINT, guía de envío, clasificación según la tesis, estimación de rúbrica, aspectos destacados del posicionamiento, decisiones de envío, procedencia de la construcción) más los documentos PRINT, ATS y CoverLetter (carta de presentación) y las versiones renderizadas en PDF.

## Lo que todo módulo da por sentado

1. Asegúrese de que su registro de hechos (my-data/fact_registry.json) esté pegado o adjunto en el chat, junto con `principles.md` y `semantic_equivalence_map.md`, más sus notas de sesión si las lleva.
2. Todas las afirmaciones reflejan autoridad de decisión e involucramiento reales (Principio #1, antialucinación).
3. Las decisiones de encuadre bloqueadas en sus notas no son negociables (Principio #10).
4. La salida respeta la rúbrica de viñetas Action (Acción), Scope (Alcance), Outcome (Resultado), Evidence (Evidencia), Tech/Method (Tecnología o método) con el límite estricto de 40 palabras (Principio #5).
5. Las viñetas de nivel sénior demuestran marcadores de nivel (Principio #8).
6. Las sesiones terminan con un cierre explícito mediante el Módulo 12 (Principio #12).
7. El sistema se extiende a sí mismo según el contexto del puesto, dentro de los límites de rastreabilidad al registro de hechos (Principio #13).
8. Los entregables están limpios en ASCII y verificados en PDF (Principio #14) y respetan los estándares de identidad: nombre completo, ubicación geográfica en el encabezado, bloque de contacto (Principio #15).

## Tesis de carrera (estrella polar)

Defina su propia tesis de carrera: 2 o 3 rutas de destino legítimas. El Módulo 13 clasifica cada puesto objetivo contra ellas. Toda extensión de encuadre se alinea con al menos una de las rutas.

EJEMPLO, reemplácelo con sus propias rutas:

- **Ruta A: Liderazgo sénior de personas** (Director, luego VP / SVP)
- **Ruta B: Autoridad técnica sénior** (Director, luego Principal / Distinguished IC, contribuidor individual)
- **Ruta C: Consultoría independiente / Liderazgo de práctica**

Use `templates/career_thesis_template.md` para escribir la suya y guárdela en `my-data/`.

## Disciplina de revisión permanente

- **Panel de personas lectoras (Módulo 06, según el modo).** Las construcciones FULL reciben tres lecturas simuladas independientes (lectura rápida de 6 segundos del reclutador, simulación de análisis del ATS, lectura del gerente de contratación); las construcciones FAST reciben reclutador + ATS + la pasada dirigida de riesgo del HM, incondicionalmente. Los hallazgos HIGH (altos) sin resolver bloquean el empaquetado en todos los modos.
- **Verificación de salud del espacio de trabajo** al inicio y al cierre de la sesión: cada `final/[nombre-del-puesto]/` tiene un HANDOFF_MANIFEST.md; no existe en disco ningún paquete entregado que sus notas de sesión desconozcan; `my-data/` está al día. Rápida y silenciosa salvo que algo falle.
- **Revalidación de la doctrina** cada cinco cierres o cada mes, lo que ocurra primero: revisión de coherencia del pipeline + revisión de la doctrina del panel de personas lectoras + auditoría de estructura. (OPCIONAL; se vuelve útil cuando usted maneja varias postulaciones a la vez.)

## Postulaciones en frío

La mayoría de los puestos objetivo pasan por un portal sin recomendación. La disciplina que sustituye a la calidez:

- **Preguntas eliminatorias.** La KNOCKOUT PLAYBOOK vive en `ats_upload_notes.md` (campos de título universitario, campos de salario, presentación de la educación). El Módulo 01 señala el riesgo de eliminación por título en la ingesta; revise la JD en busca de preguntas eliminatorias antes de construir.
- **Las palabras clave MUST-HAVE aparecen de forma literal en la versión ATS.** La cobertura por sinónimos no basta para los filtros del lado del analizador (parser); el Módulo 02 corre la verificación literal.
- **La carta de presentación es un factor de desempate en portales fríos.** Se construye cuando el portal tiene un campo para ella (Módulo 08, COLD PORTAL MODE); la investigación de la empresa (Módulo 09, ON por defecto) alimenta tanto la carta como las respuestas de filtrado.
- **Nombres de archivo para el envío:** "[Su nombre completo] Resume - [Puesto objetivo].docx", a cargo del Módulo 11.

## Ubicación de los archivos

| Propósito | Ruta (relativa a la raíz del kit) |
|---|---|
| Biblioteca de módulos + documentos de referencia | `prompts/` |
| Manual de operación | `prompts/README.md` (este archivo) |
| Plantillas | `templates/` (fact_registry_template.json, career_thesis_template.md) |
| Sus datos privados | `my-data/` (fact_registry.json, tesis de carrera, notas de sesión, lessons_learned.md opcional); manténgala FUERA de cualquier ubicación pública |
| Borradores activos | `drafts/[nombre-del-puesto]/` |
| Paquetes entregados | `final/[nombre-del-puesto]/` con HANDOFF_MANIFEST.md |

## Sus archivos de datos

- `my-data/fact_registry.json`: la base de evidencia. Toda afirmación del currículum debe rastrearse hasta una entrada aquí. Parta de `templates/fact_registry_template.json`.
- `my-data/lessons_learned.md` (opcional): patrones reutilizables que usted confirma al cierre.
- Notas de sesión (opcional): puestos objetivo activos, decisiones de encuadre bloqueadas, registro de red de contactos, Outcome Ledger. OPCIONAL; se vuelve útil cuando usted maneja varias postulaciones a la vez.

## Titulares de los principios operativos (principles.md)

15 principios: 7 de Nivel 1 / 6 de Nivel 2 / 2 de Nivel 3. El Nivel 1 prevalece sobre el Nivel 2, que prevalece sobre el Nivel 3.

**Nivel 1 (no negociable):**
- **#1 Antialucinación** (supremo): las afirmaciones se rastrean hasta su registro de hechos; verificación en el registro antes de bloquear; confirmación específica por afirmación
- **#2 Exactitud sobre inflación**: lenguaje de alcance honesto
- **#10 Encuadre bloqueado no negociable**: se puede extender, nunca violar ni relajar
- **#12 Disciplina de cierre**: sin transiciones de estado silenciosas; las sesiones terminan mediante el Módulo 12
- **#13 Adaptación del encuadre según el puesto**: el sistema se extiende por puesto dentro de los límites antialucinación
- **#14 Disciplina de limpieza de la salida**: sin guiones largos ni guiones medios, sin flechas, sin comillas tipográficas; conteos de páginas verificados en PDF; sin líneas huérfanas
- **#15 Estándares del documento e identidad**: nombre completo "[SU NOMBRE COMPLETO]"; encabezado "[CIUDAD, ESTADO]"; "[TELÉFONO]"; [Opcional: una línea para una habilitación de seguridad (clearance) vigente o una certificación destacada, si la tiene]; reglas de uso ATS frente a PRINT

**Nivel 2 (proceso):**
Afirmaciones respaldadas por evidencia (#4), rúbrica de viñetas con límite estricto de 40 palabras (#5), alineación entre documentos (#6), interrogatorio proactivo (#7), nivelación de nivel sénior (#8), explicar antes de confirmar (#9)

**Nivel 3 (preferencia):**
Empleabilidad sobre estética (#3), estilo de interacción (#11)

## Mantenimiento

**Módulos y documentos de referencia (cambian poco):** Edite en el lugar e incremente el encabezado de versión. Si usa git, las versiones anteriores viven en el historial; si no, conserve una copia de respaldo fechada si la desea.

**Sus archivos de datos (cambian mucho):** El Módulo 12 guía al usuario durante las actualizaciones al cierre. Guarde los archivos al terminar.

**semantic_equivalence_map (cambio moderado):** Las actualizaciones se acumulan en una lista de pendientes en sus notas de sesión. Se incorporan al mapa cuando hay 5+ pendientes.

**Las reestructuraciones mayores** reciben una nota en sus notas de sesión, y la sesión que las hace termina guardando sus archivos actualizados.
