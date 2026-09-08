# Módulo 13: Calificación del puesto objetivo (13_target_qualification)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Después del Módulo 01 (intake_and_matrix), antes de la Strategy Gate (compuerta de estrategia) del Módulo 00 (Paso 2a) y del Módulo 02 (rubric_score)
**Depende de:** La salida del Módulo 01 (matriz de requisitos + familia de puestos), su tesis de carrera (my-data/career_thesis.md)

## Qué hace este módulo
Clasifica un puesto objetivo frente a su tesis de carrera y produce una recomendación explícita de perseguir / persecución estratégica / no perseguir, con su justificación. Evita gastar esfuerzo de adaptación en puestos objetivo desalineados y obliga a la claridad estratégica en los casos limítrofes. Su clasificación alimenta la Strategy Gate del Módulo 00, que propone el nivel y el modo de construcción en la única tarjeta de decisión.

## Definiciones de nivel (alimentan la Strategy Gate)
- **Nivel A** = veredicto del Módulo 13 PURSUE (perseguir) o STRATEGIC PURSUE (persecución estratégica) con una compensación que cumple o supera su mínimo, O cualquier puesto objetivo que usted declare prioritario.
- **Nivel B** = todo lo demás que usted decide perseguir.
- **Nivel C** = perseguir sin construir.
- El nivel es una propuesta de esfuerzo de construcción, no un veredicto de perseguir o no.
- **NO-BUILD (sin construcción) tiene un alcance estrictamente menor que DON'T PURSUE (no perseguir):** NO-BUILD significa "sin construcción nueva; usted aún puede perseguir el puesto con un carril existente o un artefacto de biblioteca". Es un resultado de modo de construcción en la gate card (tarjeta de la compuerta), nunca una cancelación de la persecución por brechas. Las clasificaciones y las propuestas de la compuerta INFORMAN; perseguir o no sigue siendo decisión suya.

(Los niveles y la Strategy Gate son OPCIONALES: se vuelven útiles una vez que usted maneja varias postulaciones a la vez.)

## Cuándo usarlo
- Después de que el Módulo 01 produce una matriz de requisitos para un puesto objetivo nuevo
- De forma independiente, al evaluar si postularse a un puesto antes de comprometer esfuerzo de adaptación
- Cuando un reclutador lo contacta por un puesto y usted necesita una evaluación rápida de ajuste

## Por qué existe este módulo
Sin una clasificación explícita de alineación con la tesis, cada descripción del puesto (JD) corre el riesgo de recibir adaptación sin importar su ajuste estratégico. Adaptar es costoso (en lo cognitivo y en tiempo); los puestos objetivo que no hacen avanzar su carrera son esfuerzo desperdiciado. Este módulo obliga a que la clasificación sea explícita.

---

## PROMPT PARA PEGAR EN SU CHAT DE IA

Usted opera como **Módulo 13: Calificación del puesto objetivo** para el sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/career_thesis.md`, la tesis de carrera del usuario (construida a partir de `templates/career_thesis_template.md`)
- `my-data/fact_registry.json`, en especial las decisiones de encuadre bloqueadas y el puesto actual del usuario
- `prompts/principles.md`, principios de Nivel 1
- La salida del Módulo 01 para el puesto objetivo actual (matriz de requisitos, familia de puestos, contexto de la postulación)

Su tarea: clasificar el puesto objetivo frente a la tesis de carrera del usuario y producir una recomendación de perseguir.

**Tesis de carrera (de my-data/career_thesis.md):**

Defina la tesis de carrera del usuario: 2 o 3 rutas de destino legítimas. Cada puesto objetivo se clasifica frente a ellas. Cualquiera de las rutas definidas por el usuario está dentro de la tesis.

Las tres rutas siguientes son un EJEMPLO; reemplácelas con las rutas del usuario (usan una carrera de liderazgo en ciberseguridad; reconstrúyalas para el campo del usuario):

- **Ruta A. Liderazgo sénior de personas (de Director a VP / SVP):** responsabilidad sobre P&L o presupuesto, plantilla de 25+ personas, responsabilidad de programas entre organizaciones, rendición de cuentas ejecutiva, presencia externa (consejo de administración, regulador, cliente)
- **Ruta B. Autoridad técnica sénior (de Director a Principal / Distinguished IC, colaborador individual):** autoridad técnica profunda, decisiones de arquitectura a escala, mentoría de ingenieros sénior, contenido publicado de liderazgo intelectual, experto reconocido en el dominio
- **Ruta C. Consultoría independiente / Liderazgo de práctica:** construcción de una práctica, cartera de clientes, generación de ingresos, apalancamiento de la red de contactos, encargos a nivel del consejo de administración

**Paso 1. Clasificación por ruta.**

Determine qué ruta o rutas respalda el puesto objetivo:
- Señales que coinciden con la primera ruta del usuario: Ruta A
- Señales que coinciden con la segunda ruta del usuario: Ruta B
- Señales que coinciden con la tercera ruta del usuario (si está definida): Ruta C
- Multirruta (por ejemplo, un puesto de liderazgo en una consultora podría abarcar una ruta de liderazgo de personas y una ruta de consultoría)

Si el puesto objetivo no respalda ninguna ruta, clasifíquelo como fuera de la tesis y explique por qué.

**Paso 2. Evaluación del ajuste de nivel.**

Lea el puesto actual del usuario en `my-data/fact_registry.json` (o en el archivo de la tesis de carrera). No fije ni asuma un título de puesto.

**Matiz de niveles:** si el historial del usuario incluye un cambio de nivel voluntario (por ejemplo, un título de liderazgo de personas cambiado por un título de colaborador individual sénior con compensación sin cambios), ancle las comparaciones de ajuste de nivel al alcance MÁS AMPLIO demostrado por el usuario (presupuesto, plantilla, rendición de cuentas ejecutiva), no solo al título actual. Un puesto que se lee como "salto" desde el título actual puede ser lateral o coincidencia directa frente al historial de alcance más amplio. Registre cualquier matiz de este tipo en su archivo de tesis de carrera para que se aplique de forma consistente.

Compare el nivel real del puesto objetivo con la posición actual del usuario teniendo en mente ese ancla:

- **Salto (stretch)**: mejora significativa en alcance, nivel o marca. Por lo general requiere una presentación cálida (warm intro) por la red de contactos para lograr una conversión.
- **Lateral dentro de la tesis**: mismo nivel, alcance similar, mantiene el posicionamiento en una ruta objetivo. Persígalo si es estratégico (mejora de marca, giro de industria, expansión de la red de contactos).
- **Descenso estratégico**: menor nivel o compensación, pero con una ganancia real de habilidad o posicionamiento (por ejemplo, un puesto de grado inferior que construye una habilidad emergente específica y entra a una marca más fuerte). Persígalo con los ojos abiertos.
- **Descenso sin justificación**: menor nivel o compensación sin ganancia estratégica. Por defecto: no perseguir.
- **Coincidencia directa**: mismo nivel en la ruta elegida. Por defecto: perseguir.

Use comparadores de nivel de puesto cuando sea posible: muchas empresas grandes publican sus sistemas de niveles, o estos se filtran, y los sitios públicos de comparación permiten mapear el grado de una empresa a su equivalente aproximado en otra. Señale la incertidumbre cuando un comparador sea una conjetura.

**Paso 3. Recomendación de perseguir.**

Produzca una de estas:

- **PURSUE**: ajuste claro dentro de la tesis, nivel apropiado, sin salvedades mayores
- **STRATEGIC PURSUE**: fuera de la tesis o descenso, pero con una justificación estratégica explícita que el usuario confirma (crecimiento de habilidades, entrada a una marca, expansión de la red de contactos, opcionalidad)
- **STRETCH PURSUE** (persecución como salto): mejora significativa; requiere una ruta de presentación cálida o una diferenciación fuerte
- **HOLD** (en espera): limítrofe; necesita más información o investigación antes de comprometer esfuerzo de adaptación
- **DON'T PURSUE**: fuera de la tesis sin justificación estratégica, o descenso significativo sin ganancia

**Paso 4. Justificación y riesgos.**

Para la recomendación, nombre:
- Qué ruta o rutas respalda el puesto objetivo
- Ajuste de nivel (y cómo se compara con el actual, anclado al alcance más amplio demostrado)
- Por qué esto hace avanzar (o no) la tesis de carrera
- Riesgos por señalar: brecha de compensación, geografía, desajuste de nivel, estabilidad de la empresa, ambigüedad en la definición del puesto, etc.
- Para STRATEGIC PURSUE: nombre la ganancia estratégica explícita (por ejemplo, "habilidad emergente específica, entrada a una marca más fuerte")
- Para STRETCH PURSUE: nombre qué haría realista la ruta de presentación cálida

**Paso 5. Estructura de la salida.**

```
TARGET QUALIFICATION (calificación del puesto objetivo): [Puesto] en [Empresa]

PATH CLASSIFICATION (clasificación por ruta)
- Ruta principal: [A / B / C / multi (multirruta)]
- Razonamiento de la ruta: [...]

LEVEL FIT (ajuste de nivel)
- Nivel del puesto objetivo: [...]
- Su puesto actual: [leído de my-data/fact_registry.json o my-data/career_thesis.md]
- Nota de anclaje: [cualquier matiz de niveles de la tesis de carrera, por ejemplo, anclado al alcance más amplio demostrado]
- Clasificación: [stretch (salto) / lateral on-thesis (lateral dentro de la tesis) / strategic downshift (descenso estratégico) / downshift no rationale (descenso sin justificación) / direct match (coincidencia directa)]
- Razonamiento del comparador: [...]

PURSUE RECOMMENDATION (recomendación de perseguir): [PURSUE / STRATEGIC PURSUE / STRETCH PURSUE / HOLD / DON'T PURSUE]

RATIONALE (justificación)
- Alineación con la tesis: [...]
- Valor estratégico: [...]
- Riesgos por señalar: [...]

NEXT MODULE (siguiente módulo)
- Si PURSUE / STRATEGIC PURSUE / STRETCH PURSUE: Módulo 14 (network_pathway) para la revisión de presentación cálida, luego la línea base del Módulo 02 (rubric_score)
- Si HOLD: capture las preguntas aclaratorias para el usuario antes de continuar
- Si DON'T PURSUE: documente el razonamiento en las notas de my-data; no avance el pipeline
```

**Requisitos antialucinación:**
- No invente detalles del puesto objetivo que no estén en la JD ni en la salida del Módulo 01
- No infiera comparadores de nivel sin fundamento (use equivalencias de grado conocidas; señale la incertidumbre)
- No recomiende STRATEGIC PURSUE sin que el usuario confirme la justificación estratégica
- La clasificación fuera de la tesis requiere un razonamiento explícito que el usuario pueda cuestionar
- El usuario es responsable de defender su capacidad en la entrevista; aun así, el currículum no puede atribuirle una responsabilidad histórica que no conste en el fact_registry. Si una afirmación no está en el registro ni se confirmó de forma explícita en la sesión actual, no va al papel.

---

## Entregables esperados
- Reporte de calificación de una página con clasificación + recomendación + justificación
- Cola de decisiones para que el usuario confirme o modifique
- Dirección hacia el siguiente módulo

## Conexión con otros módulos
- Lee la matriz de requisitos y la familia de puestos del Módulo 01
- Lee my-data/career_thesis.md y el puesto actual de my-data/fact_registry.json
- Alimenta al Módulo 14 (network_pathway) si se confirma la decisión de perseguir
- Alimenta al Módulo 12 (cierre): la clasificación se captura por puesto objetivo en completed_packages

## Conexión con la tesis de carrera
Este módulo es el principal garante de la disciplina de la tesis de carrera. Si los puestos objetivo se clasifican una y otra vez como STRATEGIC PURSUE o DON'T PURSUE en lugar de un PURSUE limpio, es señal de que la tesis misma necesita revisión: quizá sus rutas elegidas cambiaron, o el posicionamiento de su puesto actual evolucionó.
