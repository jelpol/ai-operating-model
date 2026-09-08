# Módulo 02: Calificación por rúbrica (02_rubric_score)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 2 de 15 (también se ejecuta después de content_build para la calificación final)
**Depende de:** Matriz de requisitos del Módulo 01, semantic_equivalence_map.md

## Qué hace este módulo
Califica una versión del currículum contra una matriz de requisitos. Produce un % de efectividad ponderado, un desglose por grupo, una verificación de densidad de palabras clave para el sistema de seguimiento de candidatos (ATS), una verificación de diversidad de verbos, una ponderación del tercio superior (above the fold) y un reporte de brechas categorizado. Se usa tanto para la calificación de referencia como para la final. También informa un veredicto de diferenciación competitiva sobre si el tercio superior se distingue frente al conjunto de personas candidatas calificadas. Razón: el ajuste hace que el currículum pase el analizador (parser); la diferenciación consigue la primera respuesta (callback).

## Cuándo usarlo
- Después de la ingesta, para establecer la referencia de una versión de origen existente
- Después de content_build, para calificar el borrador adaptado
- De forma independiente, para auditar cualquier currículum contra una descripción del puesto (JD)

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 02: Calificación por rúbrica** del sistema de adaptación de currículum de la persona candidata.

Lea primero:
- El registro de hechos de la persona candidata. Asegúrese de que su registro de hechos (my-data/fact_registry.json) esté pegado o adjunto en este chat.
- `prompts/principles.md`
- `prompts/semantic_equivalence_map.md`, para el reconocimiento de sinónimos. (Los ejemplos de ese mapa usan puestos de ciberseguridad; reconstruya las listas para el campo del usuario.)

Entradas que necesita:
1. La matriz de requisitos del Módulo 01 (o pegada en el chat)
2. La versión del currículum por calificar (ruta de archivo o pegada en el chat)
3. Si se trata de una calificación BASELINE (de referencia) o FINAL

**Método de calificación: escala 0/1/2/3.**

Para cada requisito de la matriz, califique el contenido del currículum:
- **0 puntos**: ausente
- **1 punto**: mencionado pero genérico, sin detalles concretos
- **2 puntos**: atendido de forma adecuada con herramientas nombradas, alcance o evidencia
- **3 puntos**: demostrado con fuerza mediante evidencia cuantificada, artefactos nombrados o impacto con alcance definido

Aplique los pesos por grupo:
- MUST-HAVE (indispensable): peso x3
- STRONG-SIGNAL (señal fuerte): peso x2
- NICE-TO-HAVE (deseable): peso x1

**Ponderación del tercio superior.**

El tercio superior del currículum (Resumen ejecutivo, Aspectos destacados de liderazgo o su equivalente, y la descripción del primer puesto listado) recibe un multiplicador de peso de 1.5x sobre su contenido. Tanto los reclutadores como los motores de ATS ponderan la ubicación.

Identifique el tercio superior por posición del contenido, no por posición en la página. Luego, para cualquier requisito calificado con contenido del tercio superior, multiplique la calificación de ese requisito por 1.5.

**Verificación más estricta en segunda pasada.**

Después de completar la primera pasada de calificación, haga una SEGUNDA pasada con criterios explícitamente más estrictos:
- Un "2" solo cuenta como "2" si están presentes al menos dos de {herramienta nombrada, alcance, resultado cuantificado}
- Un "3" requiere al menos tres de los cuatro: herramienta nombrada, alcance, resultado cuantificado, artefacto nombrado
- Reduzca la calificación de todo lo que no cumpla el criterio más estricto

Informe el delta entre la calificación laxa y la estricta. Si el delta > 5 puntos porcentuales, marque la calificación como "incierta, con una dispersión amplia". Esto aproxima en una sola pasada el promedio de varias ejecuciones.

Calcule: weighted_score / max_possible x 100 = % de efectividad. Informe tanto la laxa como la estricta.

**Subcalificación de diversidad de verbos.**

La diversidad de verbos es una métrica de legibilidad HUMANA, no una métrica de ATS. Los motores de ATS no califican la variedad de verbos. La razón honesta: un reclutador o gerente de contratación que lee diez viñetas que abren todas con "Dirigí" lo percibe como relleno y deja de asimilar el contenido. Varíe los verbos para el lector humano, pero nunca sacrifique una palabra clave literal requerida para mejorar esta proporción.

Cuente los verbos de acción al inicio de cada viñeta en todo el currículum. Calcule:
- unique_verbs / total_bullets = verb_diversity_ratio

Metas (PASS aprobado, WARN advertencia, FAIL reprobado):
- >= 0.6 = [PASS] buena diversidad
- 0.4 a 0.6 = [WARN] algo de repetición, considere variar
- < 0.4 = [FAIL] repetición intensa, se lee como monótono para un revisor humano

Enumere los 5 verbos más repetidos.

**Verificación de densidad de palabras clave.**

Para cada requisito MUST-HAVE, verifique si sus términos clave (tecnologías, certificaciones y marcos nombrados) aparecen >= 2 veces en el currículum. Informe POR SEPARADO las coincidencias de frase literal EXACTA y las coincidencias de sinónimos: la búsqueda del ATS que usan los reclutadores (Workday, iCIMS) es booleana literal, así que solo las ocurrencias textuales de la frase de la JD tienen garantía de aparecer en la búsqueda por palabras clave de un reclutador. Use el semantic_equivalence_map.md para identificar coincidencias de sinónimos (por ejemplo, "JML" y "joiner-mover-leaver" cuentan ambos como sinónimos de ciclo de vida de identidades), pero nunca fusione los dos conteos en una sola cifra.

Marque cualquier palabra clave MUST-HAVE que aparezca:
- 0 veces textual, 0 sinónimos: [FAIL] ausente (brecha crítica)
- 0 veces textual, con sinónimos presentes: [FAIL] falla literal (la búsqueda booleana del reclutador no la encontrará)
- 1 vez textual: [WARN] poco enfatizada
- 2+ veces textual: [PASS] adecuada

**Regla de literalidad para MUST-HAVE.**

La frase literal de la JD de cada requisito MUST-HAVE debe aparecer textualmente al menos una vez en la versión ATS (preferiblemente dos), siempre que sea honesto incluirla. Los sinónimos del mapa de equivalencia semántica cuentan para la densidad, pero nunca pueden reemplazar la última ocurrencia textual de la frase.

**Verificación de diferenciación competitiva.**

El ajuste hace que el currículum pase el analizador; la diferenciación consigue la primera respuesta. Después de calificar el ajuste, evalúe el TERCIO SUPERIOR frente al conjunto de personas candidatas calificadas para esta familia de puestos: ¿qué lleva este currículum que los currículums de las otras personas candidatas plausibles no llevarán?

Construya la lista de diferenciadores a partir del propio registro de hechos de la persona candidata; verifique cada elemento contra el registro de hechos vigente antes de acreditarlo. Ejemplos genéricos de lo que califica (reconstrúyalos para el campo y el historial del usuario): una habilitación de seguridad (clearance) vigente o una certificación principal, experiencia de liderazgo en una empresa reconocida, un arco emblemático de mejora cuantificada (por ejemplo, tiempo de ciclo reducido de meses a días), escala o alcance geográfico inusuales (despliegues globales, crecimiento organizacional a gran escala), promociones logradas para reportes directos, combinaciones poco comunes entre dominios.

Informe un veredicto:
- **STANDOUT** (destaca): dos o más diferenciadores aparecen en el tercio superior
- **COMPETENT-BUT-GENERIC** (competente pero genérico): el ajuste está presente, pero el tercio superior se lee como el del resto del conjunto
- **BURIED** (enterrado): los diferenciadores existen en el documento, pero quedan debajo del tercio superior

El veredicto se informa JUNTO AL % de efectividad; nunca ajusta la calificación mecánica (las calificaciones se mantienen comparables a lo largo del historial del paquete). Un veredicto BURIED regresa a 04_content_build para retrabajar el tercio superior.

**Reporte de brechas.**

Para cada requisito con calificación 0 o 1:
- Cite la frase de la JD
- Muestre lo que hay actualmente en el currículum (o "ausente")
- Categorice la brecha como una de las siguientes:
  - **EVIDENCE-PRESENT-BUT-UNDER-SURFACED** (evidencia presente pero poco visible): la persona candidata tiene la experiencia según el registro de hechos o el currículum de origen; el borrador actual simplemente no la hace visible
  - **EVIDENCE-LIKELY-UNDOCUMENTED** (evidencia probable no documentada): la persona candidata probablemente tiene esto, pero no está en el currículum ni en el registro de hechos. Tema para el interrogatorio.
  - **GENUINE-GAP** (brecha genuina): la persona candidata no tiene esta experiencia. Reconózcala y atiéndala en la carta de presentación.

Use el registro de hechos para fundamentar la categorización. No clasifique como GENUINE-GAP sin revisar primero el registro de hechos.

**Estructura del resultado:**

```
RUBRIC SCORE (calificación por rúbrica): [Versión del currículum] vs [Puesto objetivo]
Tipo de calificación: [BASELINE / FINAL]

OVERALL EFFECTIVENESS (efectividad general)
- Pasada laxa: [X]% ([ponderado] / [máx])
- Pasada estricta: [Y]%
- Delta: [Z] pp [STABLE (estable) / UNCERTAIN (incierta)]

PER-BUCKET BREAKDOWN (desglose por grupo)
- MUST-HAVE: [X]% laxa | [Y]% estricta
- STRONG-SIGNAL: [X]% laxa | [Y]% estricta
- NICE-TO-HAVE: [X]% laxa | [Y]% estricta

ABOVE-THE-FOLD CONTRIBUTION (contribución del tercio superior)
- El contenido del tercio superior aportó: [X] puntos de la calificación ponderada total
- Efectividad del tercio superior: [X]% del peso disponible del tercio superior capturado

VERB DIVERSITY (diversidad de verbos; métrica de legibilidad humana)
- Proporción: [X.XX] [PASS / WARN / FAIL]
- Verbos más repetidos: [verbo1 (n), verbo2 (n), ...]

KEYWORD DENSITY (densidad de palabras clave; palabras clave MUST-HAVE, conteos textual y de sinónimos informados por separado)
- [palabra clave]: textual [conteo] | sinónimos [conteo] [PASS / WARN / FAIL]

MUST-HAVE VERBATIM CHECK (verificación de literalidad MUST-HAVE; versión ATS)
- [frase literal de la JD]: [n] ocurrencias textuales [PASS >= 1, preferible 2 / FAIL 0]

COMPETITIVE-STANDOUT CHECK (verificación de diferenciación competitiva)
- Diferenciadores en el tercio superior: [lista]
- Veredicto: [STANDOUT / COMPETENT-BUT-GENERIC / BURIED]

GAP REPORT (reporte de brechas)
1. [Frase de la JD] | Actual: [extracto del currículum o "ausente"] | Calificación: [0-3] | Categoría: [...]
2. ...

PRIORITY GAPS FOR NEXT MODULE (brechas prioritarias para el siguiente módulo)
- Las 3 a 5 brechas principales que más moverían la calificación si se atendieran

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- Si es baseline y calificación < 75%: 03_proactive_interrogation
- Si es baseline y calificación >= 75%: 04_content_build
- Si es final y calificación >= 90%: 05_cross_document_alignment y luego 06_qa_gate
- Si es final y calificación < 85%: otra pasada de 04_content_build
- Si delta > 5pp (incierto): vuelva a calificar con criterios aún más estrictos antes de decidir
```

**Requisitos antialucinación:**
- No acredite una viñeta por evidencia que en realidad no está ahí.
- Use el semantic_equivalence_map.md como la AUTORIDAD sobre lo que cuenta como sinónimo. No invente equivalencias que no estén en el mapa.
- La calificación es mecánica; no la suavice para animar al usuario. Si es 61%, diga 61%.
- Cite los IDs del registro de hechos cuando acredite una viñeta por evidencia que el registro confirma.
- Si las calificaciones laxa y estricta divergen de forma significativa, el informe honesto incluye AMBAS y reconoce la incertidumbre.

---

## Entregables esperados
- % de efectividad laxo y estricto (con delta y marca de estabilidad)
- Desglose por grupo
- Contribución del tercio superior
- Subcalificación de diversidad de verbos
- Verificación de densidad de palabras clave (conteos textual y de sinónimos por separado) y verificación de literalidad MUST-HAVE
- Reporte de brechas categorizado
- Siguiente módulo recomendado específico

## Conexión con otros módulos
- Brechas EVIDENCE-LIKELY-UNDOCUMENTED: pasan a `03_proactive_interrogation`
- Brechas prioritarias: pasan a `04_content_build`
- Los deltas de calificación (de referencia a final) capturan el valor de este módulo en sus notas de sesión
- Sinónimos nuevos descubiertos durante la calificación: agréguelos a `semantic_equivalence_map.md`
