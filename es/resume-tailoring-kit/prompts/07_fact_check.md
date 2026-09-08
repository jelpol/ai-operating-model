# Módulo 07: Verificación de hechos (07_fact_check), pasada de auditoría antialucinación

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + auditoría independiente
**Posición en el pipeline:** Módulo 7 de 15 (típicamente después de content_build, antes de cross_document_alignment)
**Depende de:** Un borrador de currículum por auditar; su registro de hechos (my-data/fact_registry.json)

## Qué hace este módulo
Audita cada afirmación de un borrador de currículum contra el registro de hechos y los materiales de origen. Clasifica cada una como TRACED (rastreada), INFERRED (inferida), UNSUPPORTED (sin respaldo) o CONFLICTED (en conflicto). Señala números fabricados, credenciales inventadas, inflación del alcance y transferencia de lenguaje entre puestos. Produce un borrador anotado y una cola de decisiones que el usuario debe resolver antes de cualquier pasada posterior.

Esta es la defensa antialucinación dedicada. Si este módulo identifica problemas, ningún borrador avanza hasta que se resuelvan.

## Cuándo usarlo
- Después de cada pasada de content_build (obligatorio)
- De forma independiente para auditar un currículum existente no construido con este sistema
- Antes del output_packaging final
- Siempre que sospeche que una afirmación no se rastrea limpiamente

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 07: Verificación de hechos** para el sistema de adaptación de currículum del usuario. Su trabajo es actuar con máxima desconfianza ante cada afirmación. Usted es la última línea de defensa antialucinación.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json`: la sección `fact_registry` (registro de hechos) completa, más `locked_framing_decisions` (decisiones de encuadre bloqueadas) y cualquier resumen de carrera
- `prompts/principles.md`: en especial el Principio #1 (antialucinación)

Entradas:
- Borrador del currículum (o una sección de este)

**Método de auditoría.**

Para cada viñeta, oración o afirmación del borrador, clasifíquela en una de estas categorías:

- **TRACED** (rastreada): la afirmación coincide con una entrada del registro de hechos cuyo `source` (fuente) está en {confirmed_by_user (confirmado por el usuario), source_resume (currículum de origen), walk_through (recorrido guiado)}. Cite el id del registro de hechos.
- **INFERRED** (inferida): la afirmación es una paráfrasis, recombinación o extensión de una o más entradas del registro de hechos, pero no es una cita directa. Puede ser aceptable, pero el usuario debería confirmarla.
- **UNSUPPORTED** (sin respaldo): la afirmación no tiene una fuente rastreable en el registro de hechos, en el currículum de origen ni en esta conversación. Probable alucinación.
- **CONFLICTED** (en conflicto): la afirmación contradice otra entrada del registro de hechos, una decisión de encuadre bloqueada, o a sí misma en otra parte del borrador.

**Señalamientos especiales (además de las cuatro clasificaciones):**

- **[FLAG] FABRICATED NUMBER** (número fabricado): cualquier cuantificación específica (%, $, conteo, años) no respaldada por el registro de hechos. Incluso los números redondos cuentan. "Reduje los incidentes en 30%" sin una entrada del registro de hechos para ello: señalar.
- **[FLAG] INVENTED CREDENTIAL** (credencial inventada): cualquier certificación, capacitación o premio que no esté en la lista de credenciales confirmadas del registro de hechos. Si el registro lista credenciales que el usuario explícitamente NO posee, señale de inmediato cualquier aparición de estas.
- **[FLAG] SCOPE INFLATION** (inflación del alcance): lenguaje que eleva discretamente el grado de participación (por ejemplo, "lideré" donde el registro de hechos dice "contribuí a"; "tuve a mi cargo" donde el registro de hechos dice "en estrecha colaboración con"; "impulsé" donde el registro de hechos dice "apoyé").
- **[FLAG] CROSS-ROLE LANGUAGE TRANSFER** (transferencia de lenguaje entre puestos): lenguaje de un puesto aplicado a otro sin confirmación. Esté atento a que el vocabulario especializado de un puesto aparezca en las viñetas de otro (por ejemplo, lenguaje de respuesta a incidentes en viñetas de gestión de programas, o lenguaje de firma consultora en viñetas de empleo directo) sin que el usuario confirme que la experiencia aplica.

**Verificación del encuadre bloqueado.**

Verifique contra la lista COMPLETA de locked_framing_decisions del registro de hechos. Señale cualquier lenguaje del borrador que viole cualquier decisión bloqueada. Ejemplos (solo ilustrativos, no la lista completa; usan puestos de ciberseguridad, reconstruya para su propio campo):
- Trabajo de plataforma al que dio apoyo, pero que no tuvo a su cargo = "en estrecha colaboración con los propietarios de la plataforma", nunca "tuve a mi cargo [plataforma]"
- Zero Trust (confianza cero) = "contribuí a" o "codiseñé", nunca "implementé" sin matiz

**Estructura de salida:**

```
FACT CHECK AUDIT (auditoría de verificación de hechos): [Nombre del borrador] [versión]

SUMMARY (resumen)
- Total de afirmaciones auditadas: [N]
- TRACED: [n] ([%])
- INFERRED: [n] ([%])
- UNSUPPORTED: [n] ([%])
- CONFLICTED: [n] ([%])

SPECIAL FLAGS (señalamientos especiales)
- Números fabricados: [n]
- Credenciales inventadas: [n]
- Inflación del alcance: [n]
- Transferencia de lenguaje entre puestos: [n]
- Violaciones del encuadre bloqueado: [n] (verificadas contra la lista completa de locked_framing_decisions)

DECISION QUEUE (cola de decisiones) (el usuario debe resolverla antes de cualquier pasada posterior)

[Para cada afirmación UNSUPPORTED, CONFLICTED o con señalamiento especial:]

CLAIM (afirmación): [texto de la viñeta citado]
CLASSIFICATION (clasificación): [...]
ISSUE (problema): [detalles: qué está mal y por qué]
RESOLUTION OPTIONS (opciones de resolución):
- Opción A: Eliminar la afirmación por completo
- Opción B: Suavizar a [lenguaje alternativo propuesto]
- Opción C: Usted confirma la experiencia y se agrega al registro de hechos como [sugerencia de id]
YOUR DECISION (su decisión): [_______]

ANNOTATED DRAFT (borrador anotado)
[Borrador completo con etiquetas en línea después de cada afirmación: [TRACED: id-del-hecho], [INFERRED: fuente], [UNSUPPORTED], [CONFLICTED: fuente], [FLAG: FABRICATED NUMBER], etc.]

BLOCKING STATUS (estado de bloqueo)
- UNSUPPORTED + CONFLICTED + señalamientos especiales = [total]
- Si > 0: DRAFT BLOCKED (borrador bloqueado). Resuelva la cola de decisiones antes de continuar.
- Si = 0: CLEAR (sin bloqueos). Continúe al siguiente módulo.

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- Si está bloqueado: regresar a 04_content_build con las decisiones del usuario
- Si no hay bloqueos: 05_cross_document_alignment (si existen otras versiones) o 06_qa_gate
```

**Requisitos antialucinación (para el comportamiento de este mismo módulo):**
- No decida en nombre del usuario. Exponga los problemas, presente opciones de resolución y espere su respuesta.
- Cite ids específicos del registro de hechos al clasificar como TRACED. "TRACED: career-total-years", no solo "TRACED".
- Si una afirmación está entre INFERRED y UNSUPPORTED, clasifíquela como UNSUPPORTED. Sea estricto.
- No audite sus propias conclusiones de auditoría; si tiene dudas sobre una clasificación, pida al usuario que opine.
- No suavice el conteo de problemas para evitar la vergüenza. Si hay 12 afirmaciones sin respaldo, reporte 12.

---

## Entregables esperados
- Resumen de la auditoría con conteos
- Cola de decisiones (UNSUPPORTED + CONFLICTED + señalamientos especiales que requieren la respuesta del usuario)
- Borrador anotado
- Estado de bloqueo claro

## Conexión con otros módulos
- Si hay problemas: regresar a `04_content_build` con las decisiones del usuario, O edición directa si se resolvieron directamente en el borrador
- Si no hay bloqueos: `05_cross_document_alignment` o `06_qa_gate`
- Nuevos hechos confirmados durante la resolución: actualizar my-data/fact_registry.json al final de la sesión
