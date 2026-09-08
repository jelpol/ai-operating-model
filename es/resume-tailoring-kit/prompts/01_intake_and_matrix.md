# Módulo 01: Ingesta y matriz de requisitos (01_intake_and_matrix)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 1 de 15 (punto de entrada si no se necesita verificación de la red de contactos; después del Módulo 14 si primero se considera una ruta de presentación cálida)
**Depende de:** Ninguno (punto de entrada) O de la salida de la ruta por la red de contactos del Módulo 14

## Qué hace este módulo
Captura la descripción del puesto (JD) objetivo junto con el contexto de la postulación, descompone la JD en una matriz de requisitos ponderada, recomienda desde qué versión de origen del currículum partir, Y produce un framing_delta_report (informe de delta de encuadre) que identifica las adaptaciones a nivel de sistema que el puesto exige.

## Cuándo usarlo
- Iniciar una nueva postulación a un puesto (empiece siempre aquí, a menos que el Módulo 14 se haya ejecutado primero)
- Análisis independiente de una JD sin comprometerse a la adaptación del currículum
- Comparar los requisitos de dos puestos lado a lado

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 01: Ingesta y matriz de requisitos** del sistema de adaptación de currículum de la persona candidata.

Antes de hacer cualquier cosa, lea:
- El registro de hechos de la persona candidata. Asegúrese de que su registro de hechos (my-data/fact_registry.json) esté pegado o adjunto en este chat, junto con sus decisiones de encuadre bloqueadas y su tesis de carrera (my-data/career_thesis.md) si las guarda por separado.
- `prompts/principles.md`: en especial el Principio #1 (antialucinación), el #10 (encuadre bloqueado) y el #13 (adaptación del encuadre impulsada por el puesto)
- `prompts/semantic_equivalence_map.md`: vocabulario vigente. (Los ejemplos de ese mapa usan puestos de ciberseguridad; reconstruya las listas para el campo del usuario.)

Su trabajo: tomar la descripción del puesto que el usuario proporciona y producir un análisis estructurado que el resto del pipeline pueda consumir. Esto incluye detectar deltas de encuadre, vocabulario y ponderación según el Principio #13.

**Paso 1: capturar el contexto de la postulación.**

Pida al usuario cualquier contexto que no esté en la JD: empresa, ubicación (ciudad), fecha límite de postulación, expectativas de compensación, consideraciones sobre el periodo de preaviso, flexibilidad geográfica, nombre del reclutador o del gerente de contratación (si se conoce), canal de postulación (Workday/Greenhouse/Lever/etc.). Si el usuario dice "omite el contexto por ahora", anótelo y proceda.

**Capture siempre la URL de la vacante** (el enlace a la página del puesto, y el enlace a la publicación de LinkedIn si fue ahí donde el usuario la encontró) y regístrela al inicio del texto de la JD que guarde. Las vacantes se retiran o dejan de poder encontrarse mediante búsqueda web, y usted necesitará el enlace el día del envío. Si el usuario pegó la JD sin enlace, pídaselo junto con el resto del contexto.

**Paso 2: descomponer la JD en una matriz de requisitos.**

Lea la JD con atención. Extraiga cada requisito, responsabilidad y calificación. Clasifique cada uno en:
- **MUST-HAVE** (imprescindible): mínimos explícitos (años de experiencia, tecnologías nombradas, certificaciones nombradas, alcance especificado). Criterios de descarte del reclutador.
- **STRONG-SIGNAL** (señal fuerte): enfatizado en el cuerpo de la JD aunque no sea un mínimo. Cosas como "usted dirigirá X" o "experiencia profunda en Y".
- **NICE-TO-HAVE** (deseable): mencionado pero de menor prioridad. Suele aparecer como "bonus" o en las secciones de "plus" o "preferido".

Para cada requisito, capture la frase literal de la JD Y la capacidad subyacente que evalúa. Ejemplo: "10+ años en gobernanza de identidades" se descompone en años más capacidad (gobernanza de identidades).

**Paso 3: identificar la familia de puestos.**

OPTIONAL (opcional): se vuelve útil cuando usted maneja varias postulaciones a la vez. Si el usuario mantiene una biblioteca de versiones de currículum dirigidas (por ejemplo, archivos "[SuNombre]-[FamiliaDePuestos].docx" como una versión de liderazgo de personas, una versión de autoridad técnica, una versión de gestión de programas), empareje la JD con una de ellas:
- [Familia de puestos 1] ([SuNombre]-[FamiliaDePuestos1])
- [Familia de puestos 2] ([SuNombre]-[FamiliaDePuestos2])
- [Familia de puestos 3] ([SuNombre]-[FamiliaDePuestos3])

Si la JD no coincide claramente con ninguna familia existente, márquela como NEW FAMILY ROLE (puesto de familia nueva) y recomiende desde qué versión existente partir, con razonamiento. Si el usuario tiene un solo currículum de origen, esa es la versión de partida por defecto; anote qué familia de puestos representa esta JD para que la biblioteca pueda crecer con el tiempo.

**Paso 4: señalar qué tiene de singular esta JD.**

¿Qué enfatiza esta JD que la familia de puestos estándar no? Por ejemplo, una industria específica, un área emergente (agentes de IA, poscuántico), un régimen de cumplimiento específico (CMMC, FedRAMP), dimensiones de alcance inusuales. Estos elementos necesitarán atención dirigida más adelante en la construcción del contenido.

**Paso 5: verificación de alineación con la tesis de carrera.**

Defina la tesis de carrera del usuario: 2 o 3 rutas de destino legítimas. Cada puesto objetivo se clasifica contra ellas. Compare el puesto con las rutas de la tesis de carrera del usuario (my-data/career_thesis.md).

EJEMPLO, sustitúyalo por las rutas del usuario:
- Ruta A (liderazgo sénior de personas hacia VP)
- Ruta B (autoridad técnica sénior hacia contribuidor individual principal, Principal IC)
- Ruta C (consultoría independiente / liderazgo de práctica)

Anote qué ruta o rutas respalda el puesto. Si el puesto no respalda claramente ninguna ruta, márquelo para revisión en el Módulo 13 (target_qualification).

**Paso 6: detección de deltas de encuadre (Principio #13).**

Compare los conceptos y el vocabulario que enfatiza la JD con el estado actual del sistema. Produzca un framing_delta_report que identifique las adaptaciones necesarias.

### 6a. Nuevos encuadres detectados

Revise la JD en busca de conceptos que requieran patrones de articulación que no están actualmente en sus decisiones de encuadre bloqueadas. Para cada uno:
- Cite la frase de la JD que introduce el concepto
- Verifique si aplica algún encuadre bloqueado vigente (por ejemplo, "arquitectura nativa de la nube" podría estar parcialmente cubierta por un encuadre existente, o podría ser genuinamente nueva)
- Si se necesita un encuadre NUEVO, proponga uno derivado de la experiencia real de la persona candidata en el registro de hechos
- Formato: `{clave}: "{lenguaje de encuadre propuesto}"`
- Ejemplo (ciberseguridad; reconstrúyalo para el campo del usuario): `cloud_security_architecture: "Aplicó principios de seguridad en la nube en estrecha colaboración con los equipos de ingeniería de plataformas en la nube; contribuciones a nivel de diseño a la gobernanza multinube; NO trabajo de configuración como ingeniero de nube contribuidor individual (IC)."`

**Verificación antialucinación:** el encuadre propuesto debe rastrearse hasta el registro de hechos. Si el registro de hechos de la persona candidata no respalda el concepto, esto es una GENUINE GAP (brecha genuina) para la carta de presentación, no un encuadre que agregar.

### 6b. Nuevo vocabulario detectado

Revise la JD en busca de términos técnicos, acrónimos o frases del dominio que no estén en `semantic_equivalence_map`. Para cada uno:
- Cite el término
- Anote la frecuencia con que aparece en la JD
- Proponga su pertenencia a un grupo de sinónimos (un grupo existente si está relacionado, o uno nuevo si el dominio es genuinamente novedoso)
- Ejemplo: `"CNAPP" aparece 4 veces: proponer el nuevo grupo de sinónimos "Plataformas de seguridad en la nube" con: CNAPP, CWPP, CSPM, protección de aplicaciones nativas de la nube`

### 6c. Ajustes a la ponderación de la rúbrica

Identifique si el énfasis de esta JD sugiere una ponderación no estándar de la rúbrica:
- ¿La JD asigna a alguna capacidad una ponderación mayor de lo habitual para esta familia de puestos?
- ¿La parte superior visible (el tercio superior del currículum) debería priorizar una capacidad específica para este puesto?
- ¿Hay elementos MUST-HAVE estándar que esta JD trata como opcionales (es decir, que pueden condensarse)?

Ejemplo de salida: `"Este puesto pondera 'arquitectura nativa de la nube' como una de las 3 capacidades principales: la ponderación de la parte superior visible debería asegurar que al menos una viñeta del resumen ejecutivo o del primer puesto listado lo demuestre. El encuadre estándar de plataformas heredadas puede condensarse."`

### 6d. Entregar el framing_delta_report

```
FRAMING DELTA (delta de encuadre): [Puesto] en [Empresa]

NEW FRAMINGS DETECTED (nuevos encuadres detectados)
[Para cada uno:]
- Concepto: [frase de la JD]
- Coincidencia con encuadre bloqueado vigente: [none (ninguna) / partial (parcial), explique / yes (sí), no requiere acción]
- Encuadre propuesto: {clave}: "{lenguaje}"
- Trazabilidad al registro de hechos: [id de la entrada, o GENUINE GAP si no es rastreable]

NEW VOCABULARY DETECTED (nuevo vocabulario detectado)
[Para cada uno:]
- Término: [...]
- Frecuencia en la JD: [N]
- Grupo de sinónimos propuesto: [grupo existente más la adición, o grupo nuevo]

RUBRIC WEIGHTING ADJUSTMENTS (ajustes a la ponderación de la rúbrica)
- [ajustes con su razonamiento]

CAREER THESIS ALIGNMENT (alineación con la tesis de carrera)
- Ruta(s) respaldada(s): [A / B / C / multi (varias) / none (ninguna)]
- Recomendación: [continuar al Módulo 13 para calificación / fuera de tesis, pausar]
```

**Paso 7: entregar la matriz completa.**

```
APPLICATION CONTEXT (contexto de la postulación)
- Empresa: [nombre]
- Puesto: [título exacto]
- Ubicación: [...]
- Fecha límite: [...]
- Expectativas de compensación: [...]
- Notas de preaviso / geografía: [...]
- Reclutador / gerente de contratación: [...]
- Canal de postulación: [...]

REQUIREMENTS MATRIX (matriz de requisitos)

MUST-HAVE (criterios de descarte del reclutador)
1. [frase literal]: [capacidad evaluada]
2. ...

STRONG-SIGNAL (enfatizado en la JD)
1. ...

NICE-TO-HAVE (preferido, no requerido)
1. ...

ROLE FAMILY RECOMMENDATION (recomendación de familia de puestos)
- Principal: [nombre de la versión] porque [razonamiento]
- Alternativa a considerar: [si la hay]
- Se necesita familia nueva: [yes (sí) / no; si es yes, explique]

UNIQUE TO THIS JD (singular de esta JD, frente a la familia de puestos estándar)
- ...

CAREER THESIS ALIGNMENT
- Ruta(s) respaldada(s): [...]

[Inserte aquí el framing_delta_report completo del Paso 6]

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- Si framing_delta tiene elementos nuevos sustanciales, pasar a 13_target_qualification (clasificar contra la tesis)
- Si framing_delta es ligero Y está alineado con la tesis, pasar a 02_rubric_score (calificación de línea base)
- Si framing_delta tiene elementos GENUINE GAP, marcar para la estrategia de la carta de presentación
```

**Requisitos antialucinación:**
- No invente requisitos que no estén en la JD. Cite la frase literal.
- No infiera capacidades que no puedan evaluarse a partir de la redacción de la JD.
- Si la JD es ambigua respecto a un requisito (por ejemplo, "experiencia profunda en la nube" sin especificar cuál nube), señale la ambigüedad, no adivine.
- Para framing_delta: NO proponga encuadres que no se rastreen hasta el registro de hechos. Las brechas genuinas siguen siendo brechas genuinas.
- Para el vocabulario: NO agregue a semantic_equivalence_map términos que no tengan relaciones semánticas claras con los grupos existentes.

**Al terminar el trabajo de este módulo:** pregunte al usuario si la matriz Y el framing_delta_report son correctos antes de recomendar el siguiente módulo. El usuario debe poder objetar las decisiones de clasificación por categoría y los encuadres propuestos.

---

## Entregables esperados
- Matriz de requisitos estructurada (3 categorías)
- Recomendación de familia de puestos con razonamiento
- Contexto de la postulación capturado (para sus notas de sesión)
- Lista de elementos singulares frente a la familia de puestos estándar
- Nota de alineación con la tesis de carrera
- Framing_delta_report (nuevos encuadres, vocabulario, ajustes a la ponderación de la rúbrica)

## Conexión con otros módulos
- La salida alimenta a `13_target_qualification` si framing_delta es sustancial O la alineación con la tesis no está clara
- La salida alimenta a `02_rubric_score` si se pasa directamente a la calificación
- Framing_delta_report: se captura para que el Módulo 12 incorpore de forma definitiva las extensiones confirmadas
- Contexto de la postulación: a sus notas de sesión en my-data/ (con el contexto completo del delta)
- Elementos singulares: a `04_content_build` para atención dirigida
- Alineación con la tesis de carrera: se rastrea con las notas del puesto objetivo
