# Módulo 09: Investigación de la empresa (09_company_research)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Invocable; DEFAULT ON (activado de forma predeterminada) para puestos objetivo que se persiguen seriamente
**Posición en el pipeline:** Se ejecuta antes de cover_letter_build o antes de interview_prep
**Depende de:** Nombre de la empresa objetivo

## Qué hace este módulo
Realiza una investigación ligera y enfocada sobre una empresa objetivo, para dar especificidad a la carta de presentación y sustento a la preparación para la entrevista. Captura el liderazgo actual, las noticias recientes relevantes para la función objetivo, las señales estructurales (fusiones y adquisiciones (M&A), despidos, reorganizaciones), el contexto regulatorio y cualquier interacción previa que usted haya tenido con la empresa. El resultado es aproximadamente 1 página de contexto útil, no un informe sectorial.

Este módulo está DEFAULT ON para puestos objetivo que se persiguen seriamente (vea prompts/README.md, el manual operativo; el orquestador no debe omitirlo para ningún puesto objetivo que usted realmente pretenda perseguir). Omítalo solo en ejecuciones de poca importancia o exploratorias. En las postulaciones en frío por portal la investigación importa aún más, no menos: alimenta la carta de presentación y las respuestas a las preguntas de filtro que sustituyen la calidez de una recomendación cálida.

Los ejemplos siguientes usan puestos de ciberseguridad; reconstruya los filtros de relevancia para su propio campo.

## Cuándo usarlo
- Antes de cover_letter_build, si desea lenguaje específico anclado en la empresa
- Antes de postulaciones en frío por portal: la investigación alimenta la carta de presentación y las respuestas a las preguntas de filtro que sustituyen la calidez de una recomendación cálida
- Antes de interview_prep: las respuestas con contexto sólido tienen mayor impacto
- De forma independiente, para refrescar la investigación entre la postulación y la entrevista

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 09: Investigación de la empresa** dentro del sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json`: verifique cualquier interacción previa con esta empresa
- `my-data/lessons_learned.md` (opcional): busque el nombre de la empresa

Entradas:
- Nombre de la empresa objetivo
- Puesto objetivo (para filtrar por relevancia)

**Comportamiento predeterminado.**

Este módulo está DEFAULT ON para puestos objetivo que se persiguen seriamente. No lo trate como una carga opcional cuando el usuario realmente pretende perseguir el puesto; omítalo solo en ejecuciones de poca importancia o exploratorias.

**Alcance de la investigación (ligera, enfocada).**

Usted dispone de búsqueda web y de obtención de páginas web. Úselas para:

1. **Liderazgo actual**: los ejecutivos más relevantes para la familia del puesto objetivo (para una contratación de director de seguridad o de IAM, eso significa CEO, CISO, CIO y CHRO; ajuste según el campo del usuario). Confirme los nombres y su vigencia.
2. **Noticias recientes relevantes para la función**: últimos 6-12 meses: incidentes, contrataciones importantes en la función objetivo, adopción de tecnología, asuntos regulatorios.
3. **Señales de estructura de la empresa**: actividad pública de M&A, desinversiones, despidos, reorganizaciones (relevantes para saber si el puesto está en un entorno estable o sujeto a cambios constantes).
4. **Contexto sectorial y regulatorio**: qué régimen regulatorio aplica (FFIEC, SEC, HIPAA, etc.) y cuál es el perfil de riesgo principal.
5. **Señales de cultura a partir de fuentes públicas**: solo a alto nivel. Evite los detalles de Glassdoor; cite comunicados de la empresa, declaraciones públicas del liderazgo y cobertura sectorial de buena reputación.
6. **Interacción previa**: consulte el registro de hechos: ¿el usuario ha trabajado con esta empresa o para ella (como empleador, cliente, cliente de consultoría o proveedor)? Si no está claro, pregunte directamente al usuario.

**Disciplina de alcance.**

Esta es una pasada de investigación de 5-10 minutos, no un análisis bursátil de Wall Street. El entregable es 1 página de contexto útil. Si no encuentra algo material en 2-3 búsquedas, siga adelante.

**Estructura de salida:**

```
COMPANY RESEARCH (investigación de la empresa): [Empresa]
Puesto objetivo: [puesto]
Fecha de investigación: [fecha]

LEADERSHIP (liderazgo) (última verificación [fecha], cite la fuente de cada uno)
- CEO: [nombre]
- [Titular de la función, p. ej., CISO]: [nombre o "no nombrado públicamente"]
- [Otro ejecutivo relevante]: [nombre o "no nombrado públicamente"]
- Otros relevantes: [...]

RECENT FUNCTION-RELEVANT NEWS (noticias recientes relevantes para la función) (últimos 12 meses, fuentes citadas)
1. [fecha: resumen de 1 línea], fuente: [URL o publicación]
2. ...

COMPANY STRUCTURE & STABILITY SIGNALS (señales de estructura y estabilidad de la empresa)
- Actividad de M&A: [...]
- Señales de reorganización: [...]
- Impulso de contratación en la función objetivo (si se puede encontrar): [...]

REGULATORY/INDUSTRY CONTEXT (contexto regulatorio y sectorial)
- Régimen principal: [FFIEC / SEC / HIPAA / etc.]
- Eventos regulatorios recientes: [...]

CULTURE SIGNALS (señales de cultura) (alto nivel, solo fuentes públicas)
- [observación con fuente]
- Nota: evite los detalles de Glassdoor; use comunicados de la empresa, declaraciones del liderazgo y cobertura sectorial de buena reputación

PRIOR INTERACTION (interacción previa) (del registro de hechos)
- [sí/no + detalles si la respuesta es sí; pregunte al usuario si no está claro]

KEY CONTEXT FOR COVER LETTER (contexto clave para la carta de presentación)
- Cualidad específica de la empresa que vale la pena mencionar: [...]
- Evento reciente que la persona candidata podría reconocer: [...]
- Lenguaje que la empresa usa sobre sí misma y que vale la pena reflejar: [...]

KEY CONTEXT FOR SCREENING QUESTIONS (contexto clave para las preguntas de filtro) (postulaciones en frío por portal)
- Hechos de la empresa que fortalecen las respuestas de "por qué ustedes": [...]
- Detalles que hacen que las respuestas del portal se perciban cercanas y no genéricas: [...]

KEY CONTEXT FOR INTERVIEW PREP (contexto clave para la preparación para la entrevista)
- Áreas de enfoque probables de quien entreviste, dadas las noticias recientes: [...]
- Temas por investigar a mayor profundidad antes de la entrevista: [...]
- Señales de alerta sobre las que vale la pena preguntar: [...]

LESSONS_LEARNED TO APPEND (lecciones aprendidas por añadir)
- [si surge algún patrón reutilizable]

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- 08_cover_letter_build (use la investigación para dar especificidad) O BIEN
- 10_interview_prep (use la investigación como contexto)
```

**Requisitos antialucinación:**
- Cite fuentes para cada noticia (URL o publicación + fecha)
- No infiera cambios de liderazgo a partir de datos antiguos; confirme el estado actual
- No invente afirmaciones sobre la cultura. Si no encuentra una fuente específica, omita la afirmación
- Si la interacción previa no puede confirmarse desde el registro de hechos, pregunte directamente al usuario; no suponga
- Si la investigación no arroja nada material en una sección, dígalo. No rellene.

---

## Entregables esperados
- Documento de contexto de la empresa de 1 página
- Elementos específicos para la carta de presentación y las respuestas a preguntas de filtro
- Elementos específicos para la preparación para la entrevista
- Entradas opcionales para lessons_learned

## Conexión con otros módulos
- Salida hacia `08_cover_letter_build` (toque específico de la empresa; calidez en las preguntas de filtro para postulaciones en frío por portal)
- Salida hacia `10_interview_prep` (contexto para las respuestas a escenarios)
- Patrones nuevos hacia `my-data/lessons_learned.md` (opcional)
