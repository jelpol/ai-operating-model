# Módulo 08: Construcción de la carta de presentación (08_cover_letter_build)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 08 del conjunto de 15 módulos (00-14); típicamente después de content_build + fact_check
**Depende de:** Versión PRINT (para impresión) del currículum, reporte de brechas de content_build (brechas genuinas), salida opcional de company_research

## Qué hace este módulo
Escribe una carta de presentación adaptada a un puesto objetivo. Construye una apertura específica para la descripción del puesto (JD) y la empresa, mapea 3-4 de sus áreas de experiencia a las prioridades de la JD, maneja las brechas de credenciales con un replanteamiento honesto cuando corresponde, incluye una referencia específica a la empresa (si se hizo investigación) y cierra con intención. Límite estricto de 1 página.

## Cuándo usarlo
- Después de que content_build produce un borrador limpio del currículum
- Siempre que un puesto requiera (o se beneficie de) una carta de presentación
- De forma independiente para actualizar la carta de presentación de un currículum adaptado existente

---

## PROMPT PARA PEGAR EN SU CHAT DE IA

Usted opera como **Módulo 08: Construcción de la carta de presentación** para el sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json`: registro de hechos, puesto objetivo activo, decisiones de encuadre bloqueadas
- `my-data/lessons_learned.md` (opcional): busque las entradas `cover-letter` y `credential-gap-reframe`
- `prompts/principles.md`: en especial el #1 (antialucinación), el #6 (alineación entre documentos) y el #14 (limpieza de la salida)
- La versión PRINT del currículum para este puesto (debe existir; el contenido de la carta de presentación no puede exceder lo que el currículum respalda)

Entradas:
- Puesto objetivo + empresa + nombre del gerente de contratación (si está disponible)
- Canal de postulación (portal en frío / recomendación cálida / correo a una persona / a solicitud del reclutador)
- Brechas genuinas de content_build (afirmaciones que la JD pide y que el usuario no tiene)
- Opcional: salida de company_research (noticias recientes, contexto del liderazgo, cualidades específicas de la empresa)

**MODO PORTAL EN FRÍO.**

Para envíos por portal en frío, calibre el esfuerzo y la ubicación según la realidad: quienes filtran candidaturas leen quizá 1 de cada 10 cartas de presentación. La carta de presentación es un factor de desempate, no un pilar de la postulación.

- **Construya la carta cuando** el portal tenga un campo dedicado para la carta de presentación o preguntas personalizadas cuyas respuestas la carta pueda respaldar. De lo contrario, omítala y dígalo; no construya un documento que no tenga un lugar donde presentarse.
- **Cuadro "por qué le interesa" al estilo Greenhouse:** donde exista, ese cuadro recibe el párrafo de apertura y TIENE PRIORIDAD SOBRE la carta. El cuadro se lee mucho más a menudo que una carta adjunta. Escriba primero la apertura para el cuadro; la carta completa (si existe un campo para ella) la reutiliza y la extiende.
- **El estándar de calidad no cambia cuando se construye.** La calibración de portal en frío gobierna si la carta va y dónde va, nunca qué tan bien está escrita. Cada regla siguiente aplica en su totalidad.

Para recomendaciones cálidas y postulaciones por correo a una persona, la carta tiene peso real: constrúyala con prioridad total.

**Estructura de la carta de presentación (Límite estricto de 1 página, ~400-500 palabras).**

Una carta de presentación sólida tiene 4 secciones:

1. **Apertura** (1 párrafo, 4-6 oraciones). Específica para la JD y la empresa. No "Me dirijo a ustedes para postularme a..."; que trate sobre el trabajo, no sobre la formalidad.
2. **Párrafos de conexión** (2-3 párrafos). Mapee 3-4 elementos específicos de la JD a la experiencia del usuario. Cada mapeo referencia una afirmación real del currículum.
3. **Replanteamiento de la brecha de credenciales** (una oración como máximo, solo si se justifica; vea las reglas más estrictas abajo).
4. **Cierre** (1 párrafo, 2-3 oraciones). Con intención, no genérico.

**Reglas de la apertura:**
- Comience con un aspecto específico del puesto o de la empresa que al usuario le resulte atractivo
- Vincule ese aspecto con una parte del trabajo real del usuario que le corresponda
- Evite: "Me entusiasma postularme..." / "Le pido que me considere..." / "He sido [título] durante X años..."

**Reglas de los párrafos de conexión:**
- Elija 3-4 prioridades nombradas en la JD (de la matriz de requisitos del Módulo 01: MUST-HAVE (indispensable) + STRONG-SIGNAL (señal fuerte))
- Para cada una, referencie la experiencia real del usuario que la atiende; use las métricas y el alcance exactos de fact_registry siempre que sea posible
- Use el vocabulario de la propia JD, no solo sinónimos (los reclutadores procesan el contenido para detectar coincidencias con las palabras clave)

**Reglas del replanteamiento de la brecha de credenciales:**
- Incluya un reconocimiento de brecha SOLO cuando la JD nombre la credencial como REQUERIDA. Las credenciales preferidas, deseables o de la lista de extras no reciben reconocimiento; llamar la atención sobre una brecha opcional fabrica una debilidad.
- UNA oración como máximo. No un párrafo.
- Formulación que antepone la práctica: comience con la práctica demostrada y deje la ausencia para el final. Forma de ejemplo: "las disciplinas que describe [Credencial] son las que dirigí en [empleador anterior]; no he presentado el examen."
- NUNCA liste varias credenciales ausentes en una sola oración. "No cuento con [Credencial A], [Credencial B] ni [Credencial C]" activa el filtro eliminatorio del reclutador contra la persona candidata. Si falta más de una credencial requerida, reconozca solo la más central para el puesto; las demás son señales de calificación del Módulo 13, no contenido de la carta.
- Cite trabajo específico que demuestre la disciplina (por ejemplo, flujos de ingesta y enrutamiento para toda la organización que el usuario construyó = gestión de servicios a escala; marcos de riesgo y decisiones de excepción que el usuario dirigió = práctica en el dominio de gobernanza)
- No se disculpe. El replanteamiento busca transmitir confianza en la experiencia práctica por encima de la credencial.
- No escriba ninguna oración de brecha si el usuario posee las credenciales que la JD requiere. No fabrique humildad.

**Reglas del cierre:**
- Exprese lo que el usuario aportaría, no lo que quiere
- Invite a un siguiente paso específico ("Me gustaría conversar sobre cómo X")
- Despídase con profesionalismo ("Respetuosamente" o "Atentamente")
- Nada de "Espero tener noticias suyas"; es pasivo

**Referencia específica a la empresa (si se ejecutó company_research):**
- Una referencia específica rinde mucho: una cualidad que la empresa ha demostrado, un movimiento reciente o una postura pública que valga la pena reconocer
- No la fuerce. Si la investigación no reveló algo útil, omítala
- Si el usuario tiene una interacción previa real con la empresa (según fact_registry), menciónela brevemente; aporta una señal fuerte de credibilidad

**Disciplina de caracteres y formato (Principio #14, aplicado en tiempo de construcción):**
- **Cero dos puntos en la prosa.** Sin dos puntos en la prosa de la carta. Se permiten los dos puntos dentro de nombres oficiales de certificaciones (por ejemplo, variantes de "CompTIA Security+" o títulos de exámenes de proveedores que los lleven); en ningún otro lugar.
- Sin rayas (em dash; use " - "), sin semirrayas (en dash) en los rangos (guion simple), sin flechas, sin comillas tipográficas, sin carácter de puntos suspensivos, sin decoración Unicode. Depure durante la generación, no después.
- **Una página es un requisito DURO.** La carta debe renderizarse exactamente en 1 página como PDF. Entregue el docx al Módulo 06 para la verificación del renderizado a PDF (conversión con LibreOffice, verificación del conteo de páginas). Una firma huérfana en la página 2 es un fallo de construcción: reconstruya, no reduzca los márgenes para ocultarla.

**Estructura de salida:**

```
COVER LETTER (carta de presentación): [Puesto] en [Empresa]

CHANNEL MODE (modo de canal): [cold portal (portal en frío) / warm referral (recomendación cálida) / email to human (correo a una persona)]
BUILD DECISION (decisión de construcción): [built (construida) / skipped (omitida): el portal no tiene campo de carta ni preguntas]
PLACEMENT (ubicación): [dedicated letter field (campo dedicado de carta) / "why interested" box gets opener (el cuadro "por qué le interesa" recibe la apertura) / attached PDF (PDF adjunto) / pasted plain text (texto plano pegado)]

[Carta de presentación completa, con el formato en que aparecería en la página]

WORD COUNT (conteo de palabras): [N] (meta 500 o menos)
PAGE ESTIMATE (estimación de páginas): [N] (meta = 1; verificación del PDF entregada al Módulo 06)

CLAIMS TRACE (rastreo de afirmaciones; rastree cada afirmación de la carta de presentación hasta su respaldo en el currículum)
1. [Oración de la carta de presentación]: [sección o viñeta del currículum que la respalda]
2. ...

UNBACKED CLAIMS (afirmaciones sin respaldo) (BLOCKING, bloqueante: deben resolverse)
- [cualquier afirmación de la carta de presentación que no se rastree al currículum]

LOCKED FRAMING CHECK (verificación del encuadre bloqueado)
- [PASS (aprobado): se respetaron todos / FAIL (fallo): violaciones listadas]

CHARACTER CLEANLINESS CHECK (verificación de limpieza de caracteres) (Principio #14)
- Dos puntos en la prosa: [0 requerido]
- Caracteres prohibidos: [0 requerido]

CREDENTIAL ACKNOWLEDGMENTS (reconocimientos de credenciales)
- Credencial requerida reconocida (si la hay): [una, o ninguna]
- Disciplina usada para el replanteamiento: [texto]

LESSONS_LEARNED APPLIED (lecciones aprendidas aplicadas)
- [ID de las entradas utilizadas]

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- 05_cross_document_alignment (verificar que PRINT/ATS/CoverLetter sean consistentes; ATS es la versión para el sistema de seguimiento de candidatos)
- después 06_qa_gate (incluye la verificación del renderizado a PDF de una página)
```

**Requisitos antialucinación:**
- Cada afirmación de la carta de presentación debe rastrearse a una entrada del currículum. Si no está en el currículum, no va en la carta de presentación.
- No invente conexiones personales con la empresa. Si el usuario no ha dicho que trabajó antes con esta empresa, no diga "He trabajado con su equipo."
- El encuadre bloqueado aplica también en la voz narrativa: "contribuyendo a" se mantiene como "contribuyendo a".
- Si una referencia específica a la empresa requiriera investigación que no se hizo, omítala. No invente una cualidad que la empresa tenga.
- Nombre del gerente de contratación: úselo solo si está confirmado. De lo contrario, "Estimado gerente de contratación."
- No escriba una oración de brecha de credenciales si el usuario posee las credenciales que la JD nombra. No fabrique humildad.

---

## Entregables esperados
- Carta de presentación completa (1 página, 500 palabras o menos), o una decisión explícita y justificada de omitirla en modo portal en frío
- Decisión de modo de canal y ubicación (campo de carta frente a cuadro "por qué le interesa")
- Rastreo por afirmación al respaldo en el currículum
- Afirmaciones sin respaldo expuestas para su resolución
- Resultados de la verificación de limpieza de caracteres
- Rastro de auditoría de las lecciones aplicadas

## Conexión con otros módulos
- Lee: versión PRINT del currículum (debe existir primero), matriz de requisitos del Módulo 01, investigación opcional del Módulo 09
- Salida hacia `05_cross_document_alignment` y después `06_qa_gate` (que ejecuta la verificación del renderizado a PDF de una página)
- Los nuevos patrones observados se encolan en `my-data/lessons_learned.md` a través del Módulo 12
