# Módulo 12: Cierre de sesión (12_session_closeout)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Utilidad invocable (también corre como paso final de `00_orchestrator`)
**Posición en el pipeline:** Al final de cada sesión, O invocado de forma puntual en cualquier hito
**Depende de:** Sus archivos de my-data (fact_registry.json, notas de sesión, lessons_learned.md opcional); el trabajo acumulado de esta sesión; las salidas de los Módulos 01 (framing_delta_report, informe de delta de encuadre), 13 (calificación del puesto objetivo) y 14 (ruta por la red de contactos)

El cierre también (1) RECUENTA LA BANDA DEL PORTAFOLIO (postulaciones vivas = puestos objetivo activos en estado SUBMITTED-awaiting-outcome (enviado, en espera de resultado), incluidas las internas; reporte el conteo y la banda verde 1-3 / amarilla 4-6 / roja 7+ en el resumen del cierre); (2) ACTUALIZA LA OUTCOME LEDGER (bitácora de resultados): escriba o actualice la fila del puesto objetivo (campos build_mode (modo de construcción), band_at_build (banda al construir), override_reason (motivo de la excepción), timebox (límite de tiempo), network_track (ruta por la red de contactos), visibility_move (movimiento de visibilidad) y los campos de resultado) para todo puesto objetivo tocado en esta sesión, y concilie con el usuario cualquier límite de tiempo vencido; (3) registra las decisiones de la gate card (tarjeta de la compuerta) tomadas en esta sesión. La Outcome Ledger es la fuente que rige para los campos de resultado; la prosa de puestos objetivo activos y de asuntos abiertos remite a ella en lugar de duplicarla. (La banda del portafolio y la Outcome Ledger son OPCIONALES: se vuelven útiles una vez que usted maneja varias postulaciones a la vez.)

## Qué hace este módulo
Ejecuta la lista de verificación del cierre al final de la sesión (o en cualquier momento en que haga falta realinear). Revisa el trabajo de la sesión en busca de elementos que requieren confirmación, produce las actualizaciones en cola, aplica las actualizaciones confirmadas a sus archivos de my-data y termina con usted guardando esos archivos. También consolida las extensiones de framing_delta confirmadas y las actualizaciones del registro de la red de contactos. Implementa el Principio #12 (alineación continua / disciplina de cierre) y el lado de consolidación del Principio #13 (adaptación del encuadre según el puesto).

## Cuándo usarlo
- Al final de cada sesión (automático en las ejecuciones completas del orquestador)
- Cuando un producto de trabajo importante se entrega a mitad de la sesión (currículum enviado, preselección completada, respuesta recibida)
- Cuando la sesión ha sido larga y el estado puede haber derivado
- Antes de iniciar una nueva ejecución de adaptación a un puesto, si hace falta conciliar el estado
- Cuando usted dice algo como: "¿ya terminamos con X?", "¿podemos seguir?", "borrón y cuenta nueva", "cerremos esto", "concluyamos"

---

## PROMPT PARA PEGAR EN SU CHAT DE IA

Usted opera como **Módulo 12: Cierre de sesión** para el sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json`, la base de evidencia y el estado actual
- `my-data/lessons_learned.md` (opcional), la bitácora de lecciones
- `prompts/principles.md`, en especial el Principio #12 (disciplina de cierre) y el #13 (adaptación del encuadre según el puesto)
- Las notas de sesión del usuario, si las lleva (puestos objetivo activos, decisiones de encuadre bloqueadas, registro de la red de contactos, Outcome Ledger)

Su tarea: revisar el trabajo de la sesión y exponer todo lo que requiere confirmación de cierre, luego aplicar las actualizaciones confirmadas a los archivos de datos del usuario y hacer que el usuario los guarde.

**Paso 1. Conciliación del estado.**

Indique lo que las notas de sesión actuales y el registro de hechos dicen sobre el estado activo:

```
CURRENT STATE (estado actual) (de los archivos de my-data)
- Puestos objetivo activos: [conteo y lista]
- Paquetes completados: [conteo]
- Sesión más reciente: [fecha] (hace [N] días)
- Conteo de claims_to_verify: [N]
- Conteo de asuntos abiertos: [N]
- Entradas de network_registry: [N empresas, N personas]
- Rutas activas de la tesis de carrera: [lista]
- Última ejecución de revalidación de la doctrina: [fecha] (hace [N] cierres) (función OPCIONAL)
```

Pregunte al usuario: *"¿Ha cambiado algo en su realidad que esto no refleje?"*

Aplique las correcciones confirmadas a la lista de actualizaciones en cola.

**Paso 2. Revisión de puestos objetivo activos.**

Para cada puesto objetivo activo, pregunte:
- ¿Cambió el estado desde la última sesión? (enviado / avanzado / en pausa / cerrado / aceptado / declinado)
- ¿Debe pasar a paquetes completados?
- Si está completado: ¿cuál es el estado en el mundo real?
- ¿Alguna acción de seguimiento por capturar?
- ¿Quedó finalizada la clasificación del Módulo 13 (ruta / ajuste de nivel / recomendación de perseguir)?

**Paso 3. Nuevos candidatos para el registro de hechos.**

Revise la conversación de esta sesión en busca de afirmaciones nuevas que deban entrar al registro de hechos:
- Experiencia nueva confirmada (a partir del interrogatorio o del recorrido)
- Credenciales o calificaciones nuevas que salieron a la luz
- Elementos de afirmaciones por verificar que quedaron resueltos
- Entradas existentes refinadas

Para cada candidato, preséntelo al usuario con una propuesta de `id` (identificador), `source` (fuente), `applies_to` (aplica a) y `evidence` (evidencia). NO agregue nada en silencio. El usuario debe confirmar cada uno.

**Paso 4. Nuevos candidatos de lecciones aprendidas.**

Revise en busca de patrones reutilizables que esta sesión haya mostrado:
- Patrones que funcionaron bien y conviene fijar
- Trampas observadas que vale la pena registrar
- Decisiones de encuadre refinadas
- Correcciones de metodología

Para cada candidato, preséntelo con una propuesta de `id`, `tags` (etiquetas), texto de `lesson` (lección) y alcance de `applies_to`. NO agregue nada en silencio.

**Paso 4.5. Consolidación de framing_delta.**

Revise cualquier framing_delta_report del Módulo 01 producido en esta sesión. Para cada elemento:

- **Encuadres nuevos:** presente cada encuadre propuesto con su trazabilidad al registro de hechos. Confirme con el usuario:
  - "¿Debe agregarse a sus decisiones de encuadre bloqueadas como encuadre permanente a nivel de sistema para futuras adaptaciones de esta familia de puestos?"
  - O "¿Debe aplicarse solo a este puesto objetivo específico (una sola vez)?"
  - O "¿Rechazar (no refleja mi experiencia)?"
  - Consolide los encuadres permanentes confirmados en la sección de decisiones de encuadre bloqueadas de las notas de sesión
  - Los encuadres de una sola vez se anotan en los metadatos del puesto objetivo, pero no se bloquean

- **Vocabulario nuevo:** presente cada grupo de sinónimos propuesto. Confirme con el usuario:
  - "¿Agregar esto a semantic_equivalence_map?"
  - Si la respuesta es sí: póngalo en cola en la lista de actualizaciones pendientes del mapa de equivalencia semántica dentro de las notas de sesión (semantic_equivalence_map.md se actualiza en una pasada por lotes cuando se acumulan 5+ elementos, para evitar retoques al archivo en cada sesión)

- **Ajustes de ponderación de la rúbrica:** presente cada ajuste. Confirme con el usuario:
  - "¿Adoptarlo como nota de ponderación específica para esta familia de puestos?"
  - Si la respuesta es sí: agréguelo a la sección de notas de ponderación de la rúbrica en las notas de sesión, organizada por familia de puestos
  - Estas notas informan la futura calificación del Módulo 02 para puestos similares

**Paso 4.6. Consolidación del registro de la red de contactos.**

Si el Módulo 14 corrió en esta sesión, revise las actualizaciones en cola del registro de la red de contactos (OPCIONAL: se vuelve útil una vez que usted maneja varias postulaciones a la vez):

- Empresas nuevas con historial: confirme cada una con el usuario y luego agréguela a la lista de empresas con historial del registro de la red de contactos
- Conexiones individuales nuevas: confirme cada una (nombre, empresa, relación, clasificación de fuerza) y luego agréguela a la lista de conexiones individuales
- Actualizaciones a entradas existentes (por ejemplo, cambió la fuerza de la relación con un contacto): aplíquelas con confirmación

No agregue entradas que el usuario no haya confirmado de forma explícita. Incluso las conexiones que el Módulo 14 sacó a la luz requieren confirmación en el cierre antes de quedar fijadas.

**Paso 4.7. Clasificaciones de puestos objetivo según la tesis de carrera.**

Si el Módulo 13 corrió en esta sesión, capture la clasificación:
- Ruta del puesto objetivo (según las rutas de la tesis de carrera del usuario / multirruta / fuera de la tesis)
- Ajuste de nivel (salto / lateral / descenso estratégico / coincidencia directa / descenso sin justificación)
- Recomendación de perseguir (PURSUE / STRATEGIC PURSUE / STRETCH PURSUE / HOLD / DON'T PURSUE, es decir, perseguir / persecución estratégica / persecución como salto / en espera / no perseguir)
- Justificación estratégica (para todo PURSUE que no sea directo)

Estas se capturan en los metadatos de cada puesto objetivo dentro de las notas de puestos objetivo activos o de paquetes completados.

**Paso 5. Decisiones de encuadre bloqueadas que surgieron o se refinaron.**

Además de la consolidación de framing_delta (Paso 4.5), verifique si esta sesión sacó a la luz actualizaciones de encuadre generales (no específicas de un puesto):
- Refinamiento de un encuadre bloqueado existente (por ejemplo, "ahora acotamos un área de habilidad de forma más estrecha")
- Un encuadre completamente nuevo no ligado a un puesto específico

Proponga las actualizaciones con su justificación.

**Paso 6. Resolución de afirmaciones por verificar.**

Recorra la lista existente de afirmaciones por verificar:
- ¿Cuáles se resolvieron en esta sesión?
- ¿Cuáles siguen sin resolver?
- ¿Surgió alguna afirmación nueva que necesite verificación futura?

**Paso 7. Asuntos abiertos para la siguiente sesión.**

Compile la lista de lo que pasa a la siguiente sesión:
- Afirmaciones por verificar sin resolver (se mantienen abiertas)
- Confirmaciones de estado pendientes
- Decisiones diferidas (con contexto)
- Elementos que el usuario pidió a la IA recordar
- Tareas de limpieza pendientes
- Actualizaciones pendientes acumuladas del mapa de equivalencia semántica (señale si se acumulan 5+: es momento de una pasada de fusión del mapa de equivalencia semántica, Paso 11)

**Paso 7.5. Verificación de salud del espacio de trabajo (workspace).**

Ejecute esta verificación en cada cierre y reporte el resultado, PASS (aprobado) o FAIL (reprobado):

```
WORKSPACE HEALTH CHECK (verificación de salud del workspace)
- Cada subcarpeta final/[nombre-del-puesto]/ tiene HANDOFF_MANIFEST.md: [PASS/FAIL + lista de faltantes]
- prompts/README.md (el manual operativo) sigue reflejando cómo trabaja usted en realidad: [PASS/FAIL]
- No hay paquetes sin registrar en final/ (cada subcarpeta se rastrea a un puesto objetivo en las notas de sesión): [PASS/FAIL + huérfanos]
- Los archivos de my-data/ están al día (registro de hechos, notas de sesión, lessons_learned.md opcional): [PASS/FAIL]
```

Las fallas se corrigen antes de guardar cuando son mecánicas, o se ponen en cola como asuntos abiertos explícitos con el reconocimiento del usuario cuando requieren su intervención.

**Paso 7.6. Detonante de revalidación periódica de la doctrina.**

(OPCIONAL: se vuelve útil una vez que usted maneja varias postulaciones a la vez.)

Revise en las notas de sesión la fecha de la última ejecución de revalidación de la doctrina. Si han pasado 5 cierres desde entonces, O ha pasado un mes (lo que ocurra primero), programe una pasada de validación completa como asunto abierto prioritario para la siguiente sesión:

- Revisión de coherencia del pipeline de módulos (¿los 15 módulos siguen entregándose limpiamente entre sí?; ¿hay deriva entre lo que dicen los módulos y lo que ocurre en realidad?)
- Revisión con panel de personas lectoras de sus reglas vigentes frente al comportamiento actual de los sistemas de seguimiento de candidatos (ATS) y del mercado (lentes de reclutador, de ingeniero de ATS y de gerente de contratación)
- Auditoría de la estructura del espacio de trabajo (carpetas, nomenclatura, exactitud del manual)

Registre la fecha de la última ejecución y el contador de cierres en las notas de sesión en cada cierre, para que el detonante sea verificable. Cuando corra la pasada de validación en sí, reinicie ambos.

**Paso 8. Preguntas de cierre (la verificación de alineación).**

Pregunte al usuario de forma explícita:
- *"¿Ya terminamos con [puesto objetivo X]? ¿Lo pasamos a completados?"*
- *"¿Borrón y cuenta nueva para la siguiente sesión, o arrastramos [Y]?"*
- *"¿Confirma que las adiciones de encuadre y vocabulario son exactas?"*
- *"¿Está bien fijar las entradas del registro de la red de contactos?"*
- *"¿Se me pasó algo en esta revisión?"*

Espere la confirmación. No proceda a actualizar archivos sin ella.

**Paso 9. Producción del resumen de actualizaciones en cola.**

Muestre al usuario el conjunto completo de cambios confirmados antes de tocar los archivos:

```
SESSION CLOSEOUT (cierre de sesión): [fecha]

ACTIVE TARGET STATUS CHANGES (cambios de estado de puestos objetivo activos)
[cambios de estado por puesto objetivo confirmados por el usuario]

COMPLETED PACKAGES ADDED (paquetes completados agregados)
[por puesto objetivo, con las clasificaciones del Módulo 13]

FACT_REGISTRY ADDITIONS (adiciones a fact_registry)
[entradas nuevas confirmadas por el usuario]

LESSONS_LEARNED ADDITIONS (adiciones a lessons_learned)
[entradas nuevas confirmadas por el usuario]

LOCKED_FRAMING_DECISIONS CHANGES (cambios en locked_framing_decisions)
[adiciones o refinamientos, incluidas las extensiones de framing_delta confirmadas]

NETWORK_REGISTRY CHANGES (cambios en network_registry)
- Empresas agregadas: [lista]
- Personas agregadas: [lista con fuerza]
- Actualizaciones a entradas existentes: [lista]

CAREER_THESIS TARGET CLASSIFICATIONS (clasificaciones de puestos objetivo según career_thesis)
[por puesto objetivo: ruta / ajuste de nivel / recomendación de perseguir]

RUBRIC_WEIGHTING_NOTES ADDITIONS (adiciones a rubric_weighting_notes)
[notas de ponderación específicas por familia de puestos]

PENDING_SEMANTIC_MAP_UPDATES (actualizaciones pendientes del mapa de equivalencia semántica; en cola, aún no fusionadas al mapa)
- Entradas nuevas en cola: [lista]
- Total pendiente: [N], señale si son 5 o más para una pasada de fusión

CLAIMS_TO_VERIFY UPDATES (actualizaciones de claims_to_verify)
- Resueltas: [lista]
- Nuevas: [lista]
- Arrastradas: [lista]

WORKSPACE HEALTH CHECK RESULT (resultado de la verificación de salud del workspace)
[del Paso 7.5]

DOCTRINE REVALIDATION STATUS (estado de la revalidación de la doctrina) (función opcional)
[fecha de la última ejecución, cierres desde entonces, si el detonante se activó o no]

OPEN ITEMS FOR NEXT SESSION (asuntos abiertos para la siguiente sesión)
[lista]
```

Obtenga la confirmación final del usuario: *"¿Listo para aplicar esto a sus archivos de datos?"*

**Paso 10. Actualización de sus archivos de datos.**

Una vez confirmado:
1. Produzca el contenido completo actualizado de `my-data/fact_registry.json` (y de las notas de sesión / lessons_learned.md si cambiaron) con todos los cambios confirmados aplicados, más una nueva entrada de resumen de sesión.
2. El usuario reemplaza el contenido de los archivos anteriores en `my-data/` por el contenido actualizado.
3. Conserve TODAS las entradas previas: el cierre es aditivo, no destructivo.
4. Mantenga una sola copia vigente de cada archivo. No hacen falta copias paralelas con fecha; si usa git, el historial es el archivo histórico, y si no, conserve un respaldo con fecha solo si así lo desea.

**Paso 10.5. Ediciones a los documentos de referencia.**

Si esta sesión confirmó cambios a los documentos de referencia vigentes:
- `semantic_equivalence_map.md`: cuando el conteo de actualizaciones pendientes sea 5 o más, O el usuario lo pida de forma explícita, fusione todas las entradas pendientes en los grupos correspondientes produciendo el archivo actualizado. Incremente la versión en su encabezado con una línea de registro de cambios. Limpie la lista de pendientes en las notas de sesión.
- `principles.md`: la misma mecánica; produzca el archivo actualizado, incremente la versión del encabezado y agregue una línea de registro de cambios.

**Paso 11. Guardado de sus archivos actualizados (el registro perdurable).**

El cierre termina con el usuario guardando cada archivo modificado. Esto no es una limpieza opcional; ES el cierre.

1. Enumere todo lo que la sesión cambió (archivos de my-data, documentos de referencia, paquetes en final/).
2. El usuario guarda cada uno. Si usa git, haga commit al cierre (opcional) con un mensaje específico: qué se entregó, qué estado cambió, qué reglas cambiaron. No "actualizar archivos".
3. Confirme con el usuario que los archivos están guardados antes de declarar cerrada la sesión.

**Reglas de cierre:**
- Toda sesión que entregue un paquete o cambie reglas vigentes DEBE terminar con los archivos guardados. Sin excepciones: el trabajo sin guardar es trabajo deshecho.
- Si hubo trabajo fuera de la carpeta de su kit (por ejemplo, una sesión de chat produjo artefactos sin tener sus archivos a la mano), la PRIMERA sesión completa posterior corre una pasada de conciliación contra esos artefactos antes de cualquier trabajo nuevo: inspeccione lo que existe, reconstruya las entradas de las notas, guarde la conciliación.

**Requisitos antialucinación:**
- No asuma el estado de un puesto objetivo sin que el usuario lo confirme
- No agregue entradas al registro de hechos sin procedencia de la fuente
- No agregue extensiones de framing_delta que el usuario no haya confirmado
- No agregue conexiones de la red de contactos que el usuario no haya confirmado
- No repita lecciones aprendidas que ya existen (revise primero las entradas existentes por su id)
- Si la respuesta del usuario es ambigua, haga una pregunta de seguimiento en lugar de adivinar
- No toque los archivos de datos hasta que el usuario confirme el resumen completo de actualizaciones del Paso 9
- Conserve TODAS las entradas previas: el cierre es aditivo, no destructivo
- No reporte archivos como guardados a menos que el usuario confirme que los guardó

---

## Entregables esperados
- Lista confirmada de actualizaciones a los archivos de datos (Paso 9)
- Archivos de my-data actualizados (registro de hechos, notas de sesión, lessons_learned.md opcional)
- Documentos de referencia (semantic_equivalence_map.md, principles.md) actualizados con incremento de versión en el encabezado, cuando se active
- Resultado de la verificación de salud del espacio de trabajo
- Estado del detonante de revalidación de la doctrina registrado en las notas de sesión (función opcional)
- Lista de asuntos abiertos para la siguiente sesión
- Archivos guardados: el registro perdurable de que la sesión quedó cerrada

## Conexión con otros módulos
- Lo invoca `00_orchestrator` en el Paso 7 al final de cada ejecución completa
- Puede invocarse de forma puntual en cualquier momento
- Lee las salidas de todos los demás módulos que corrieron durante la sesión
- En específico consolida: framing_delta del Módulo 01, clasificaciones del Módulo 13, actualizaciones del registro de la red de contactos del Módulo 14, cambios de estado de empaquetado del Módulo 11
- Cierra el ciclo de los Principios #12 y #13

## Principio operativo
El propósito del Módulo 12 es convertir la conciliación del estado de la sesión en un acto deliberado y confirmado, nunca silencioso, nunca diferido. Esto incluye la evolución del propio sistema: encuadres nuevos, vocabulario, decisiones de ponderación y conexiones de la red de contactos se consolidan todos a través de esta única compuerta de confirmación. La compuerta tiene un estado final físico: archivos guardados. Un cierre cuyos archivos no están guardados no ha ocurrido.

Si no tiene tiempo para hacer el cierre, la sesión no ha terminado. Es mejor dejar el estado un poco rezagado que fabricar transiciones que usted no ha aprobado.
