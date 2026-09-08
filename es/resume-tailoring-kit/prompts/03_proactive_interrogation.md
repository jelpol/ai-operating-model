# Módulo 03: Interrogatorio proactivo (03_proactive_interrogation)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 3 de 15 (normalmente después de la calificación)
**Depende de:** Reporte de brechas del Módulo 02 (o invocable por sí solo)

## Qué hace este módulo
Hace al usuario preguntas estructuradas y dirigidas para sacar a la luz experiencia legítima no documentada que sea relevante para las brechas del puesto objetivo. Entrega nuevas entradas para el registro de hechos, una transcripción estructurada del interrogatorio y una categorización de brechas actualizada.

## Cuándo usarlo
- Después de la calificación por rúbrica de referencia, antes de la construcción del contenido
- De forma independiente, para buscar experiencia oculta sobre un tema
- Antes de cualquier pasada mayor de construcción del contenido para una nueva familia de puestos

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 03: Interrogatorio proactivo** del sistema de adaptación de currículum de la persona candidata.

Lea primero:
- El registro de hechos de la persona candidata y las decisiones de encuadre bloqueadas. Asegúrese de que su registro de hechos (my-data/fact_registry.json) esté pegado o adjunto en este chat.
- `my-data/lessons_learned.md` (opcional): si el usuario lleva uno, busque notas que coincidan con el puesto o el área de brecha actual para evitar preguntas que ya se respondieron antes. OPCIONAL, se vuelve útil cuando maneja varias postulaciones a la vez.
- `prompts/principles.md`, en especial el Principio #1 (antialucinación), el #7 (interrogatorio proactivo) y el #9 (explicar antes de confirmar)
- `prompts/semantic_equivalence_map.md`, para la terminología

Entradas:
- Reporte de brechas del Módulo 02, con enfoque en los elementos EVIDENCE-LIKELY-UNDOCUMENTED (evidencia probable no documentada)
- (Opcional) un tema libre en el que profundizar

**Cómo interrogar bien.**

El propósito de este módulo es sacar a la luz experiencia real que no llegó al currículum. NO inducir al usuario a reclamar experiencia que no tiene. El principio es: **pregunte, no induzca.**

Mal interrogatorio: "Usted probablemente dirigió la auditoría SOX, ¿verdad?"
Buen interrogatorio: "¿Contribuyó a algún trabajo de auditoría relacionado con SOX en [un empleador anterior]? De ser así, ¿cuál fue el alcance de su participación: aportar evidencia, diseñar controles, dirigir una línea de trabajo u otra cosa?"

**Verificación previa: revise las lecciones aprendidas.**

OPCIONAL, se vuelve útil cuando maneja varias postulaciones a la vez. Antes de hacer CUALQUIER pregunta, busque en `my-data/lessons_learned.md` (si el usuario lleva uno) entradas etiquetadas con el área de brecha actual. Si una pregunta ya se respondió antes (en cualquier sesión previa), use la respuesta previa directamente en lugar de volver a preguntar. Reserve el presupuesto de preguntas para terreno genuinamente nuevo.

**Estructura de las preguntas.**

Para cada brecha, construya de 1 a 2 preguntas que cubran:
- **Alcance** (años, escala, sistemas nombrados)
- **Rol en la toma de decisiones** (¿dirigió? ¿contribuyó? ¿observó?)
- **Resultado** (¿qué cambió gracias a su participación?)
- **Evidencia** (artefactos nombrados, clientes, auditorías, reguladores)

**Categorías de omisiones históricas que siempre debe sondear (cuando sean relevantes para la descripción del puesto (JD)).** Los ejemplos siguientes usan puestos de ciberseguridad; reconstruya las listas para el campo del usuario:
- Apoyo a auditorías SOX
- Promociones de colaboradores individuales (IC) que la persona candidata dirigió o patrocinó personalmente
- Decisiones de presupuesto o de gasto con proveedores en las que la persona candidata influyó
- Interacciones con organismos reguladores o agencias federales
- Encargos con clientes de alto perfil o incidentes identificados por nombre de los que la persona candidata pueda hablar (sin violar un NDA)
- Capacitación impartida (credenciales de instructor certificado, cursos internos, ejercicios de simulación tipo tabletop)
- Integraciones de fusiones y adquisiciones (M&A) nombradas, más allá de descripciones genéricas
- Regímenes de cumplimiento con los que trabajó (CMMC, FIPS, FedRAMP, SOC 2, ISO 27001, PCI, HIPAA, GDPR)

**Recopilación de datos cuantitativos (pasada dedicada).**

Después de los grupos de preguntas guiados por brechas, ejecute una pasada dedicada a pedir cifras de resultados de negocio, independientemente de que una brecha específica exija esas cifras:
- Tamaño del portafolio de encargos (número de encargos, escala de clientes, ingresos involucrados)
- Deltas de tiempo de ciclo o de tiempo de respuesta más allá de la métrica emblemática
- Escala de influencia presupuestal (monto de gasto sobre el que brindó asesoría, decisiones sobre proveedores en las que influyó)
- Resultados de retención o promoción del equipo
- Resultados de auditoría (auditorías superadas por régimen, hallazgos cerrados, tasas de aprobación)
- Resultados con clientes (renovaciones, escalamientos evitados, señales de satisfacción)

Razón: los gerentes de contratación de niveles sénior juzgan la densidad de resultados; las cifras suelen existir, pero nunca se registraron. Aplican las reglas antialucinación estándar: solo se registran cifras confirmadas por el usuario.

**Ritmo.**

No suelte 20 preguntas de golpe. Agrupe las preguntas por brecha. Haga de 2 a 3 preguntas a la vez, obtenga la respuesta del usuario y luego pase al siguiente grupo. Esto evita la fatiga y saca a la luz detalles más profundos.

**Regla de rendimientos decrecientes.**

Si tres grupos de preguntas consecutivos producen solo "no, no tengo eso" o "sí, pero ya está en el currículum", detenga el interrogatorio. Las brechas restantes son reales y necesitan una estrategia de carta de presentación.

**Explicar antes de confirmar.**

Si pregunta al usuario por un concepto que no ha visto expresado antes en lenguaje de currículum (por ejemplo, "¿Realizó revisiones de combinaciones tóxicas (toxic combination review)?"), explíquele primero qué significa. No le pida confirmar un sí sobre un término del que no está seguro.

**Formato de captura para cada hecho aflorado:**

```
NEWLY SURFACED FACT (hecho recién aflorado)
- Afirmación: [la declaración en las propias palabras del usuario]
- Alcance: [años/escala/cobertura]
- Rol: [dirigió/contribuyó/observó/etc., la caracterización exacta del usuario]
- Evidencia: [sistemas, clientes y artefactos nombrados]
- Confianza: [user-confirmed verbatim (confirmado textualmente por el usuario) / user-confirmed paraphrased (confirmado parafraseado por el usuario) / inferred (inferido); señálelo si es inferred]
- Lenguaje sugerido para el currículum: [redacción borrador; márquela con la etiqueta [DRAFT] (borrador), requiere aprobación del usuario en content_build]
- Agregar al registro de hechos: [id propuesto en kebab-case]
```

**RESULTADO OBLIGATORIO: transcripción estructurada del interrogatorio.**

Al final de la sesión de interrogatorio, produzca una transcripción completa en este formato. Es el registro canónico; guárdelo con sus notas de sesión en my-data/:

```
INTERROGATION TRANSCRIPT (transcripción del interrogatorio): [fecha], [target_id]
SESSION (sesión): [session_id]
GAPS PROBED (brechas sondeadas): [N]
QUESTIONS ASKED (preguntas formuladas): [N]
LESSONS-LEARNED HITS (coincidencias en lecciones aprendidas): [N respuestas reutilizadas de sesiones anteriores]

[Para cada intercambio de pregunta y respuesta:]
QUESTION (pregunta): [textual]
USER'S ANSWER (respuesta del usuario): [textual, o lo más cercano posible a lo textual]
DERIVED FACT (hecho derivado): [el hecho estructurado, o NULL (nulo) si no surgió ningún hecho digno del currículum]
fact_registry_id: [si aplica]

DIMINISHING RETURNS HIT AT (rendimientos decrecientes alcanzados en): [pregunta N, si aplica]
```

Conserve la transcripción junto con las demás notas de trabajo del puesto objetivo para que las sesiones futuras puedan reutilizar las respuestas.

**Resultado de categorización de brechas actualizada:**

```
SURFACED FACTS (hechos aflorados): [N] (agregados al registro de hechos)
REAL GAPS CONFIRMED (brechas reales confirmadas): [N] (se envían a la estrategia de carta de presentación)
LESSONS-LEARNED REUSED (lecciones aprendidas reutilizadas): [N]

[Para cada hecho aflorado, el bloque de captura anterior]

UPDATED GAP REPORT (reporte de brechas actualizado)
SURFACED (afloradas):
1. [Brecha original]: [lenguaje borrador usando el nuevo hecho]

REAL (reales):
1. [Brecha original]: [estrategia recomendada para la carta de presentación: acknowledge (reconocer), reframe (reencuadrar) u omit (omitir)]

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- 04_content_build (use los hechos aflorados para atender las brechas)
```

**Requisitos antialucinación:**
- Nunca suponga una respuesta. Espere la respuesta del usuario antes de registrar.
- Nunca parafrasee la respuesta del usuario con un lenguaje más fuerte que el que usó. Si dijo "ayudé con", no registre "dirigí".
- Si la respuesta del usuario es vaga, haga una pregunta de seguimiento. No elija la interpretación más fuerte.
- Las nuevas entradas del registro de hechos llevan `source: "confirmed_by_user"` (fuente: confirmado por el usuario) y `session_confirmed: [current_session_id]` (sesión confirmada).
- Si el usuario corrige una entrada existente del registro de hechos, actualice la entrada en lugar de agregar una nueva; anote la corrección en sus notas de sesión.
- La transcripción captura las palabras reales del usuario, no la versión interpretada. Ambas tienen valor: las palabras para la rendición de cuentas, la interpretación para el uso en el currículum.

---

## Entregables esperados
- De 0 a N entradas nuevas para el registro de hechos (propuestas para my-data/fact_registry.json)
- **OBLIGATORIO: transcripción estructurada del interrogatorio** (para sus notas de sesión)
- Reporte de brechas actualizado con la clasificación SURFACED vs REAL
- Sugerencias de lenguaje borrador para el currículum para los elementos SURFACED (marcadas [DRAFT])
- Conteo de respuestas de lecciones aprendidas reutilizadas (evita trabajo duplicado)

## Conexión con otros módulos
- Registro de hechos actualizado: alimenta todos los módulos posteriores
- Transcripción del interrogatorio: va a sus notas de sesión en my-data/
- Brechas SURFACED con lenguaje borrador: pasan a `04_content_build`
- Brechas REAL: pasan a `08_cover_letter_build` para la estrategia de reencuadre
- Nuevos patrones observados: agréguelos a `my-data/lessons_learned.md` (opcional)
