# Comience aquí

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

Tiene en sus manos un sistema completo y funcional para adaptar su currículum a puestos específicos con un asistente de IA. Se construyó y se probó en condiciones reales durante una búsqueda de empleo de nivel sénior, y después se le retiraron los datos del propietario original para que cualquiera pueda usarlo.

No necesita conocimientos técnicos. Si puede pegar texto en un chat de IA (Claude, ChatGPT o similar) y editar un documento de Word, puede usar este sistema.

## La única regla que hace que esto funcione

Los asistentes de IA inventan cosas. Si se les deja solos, "mejorarán" su currículum con afirmaciones que usted nunca hizo, y durante la entrevista se detectará la inconsistencia en los primeros diez minutos. La respuesta de este sistema es el **registro de hechos**: un solo archivo que contiene cada hecho verdadero sobre su carrera, con sus propias palabras, confirmado por usted. Cada línea de cada currículum construido aquí debe rastrearse hasta él. Si el hecho no está en el registro, la afirmación no va en la página.

Esa es la disciplina que consigue la primera respuesta (callback) y que sobrevive a las entrevistas. Todo lo demás en el kit existe para servirla.

## Qué contiene el kit

| Carpeta | Qué contiene |
|---|---|
| `prompts/` | 15 módulos de prompts numerados más documentos de referencia. Cada uno es un prompt autónomo que usted pega en un chat de IA. `prompts/README.md` es el manual de operación completo. |
| `templates/` | Un registro de hechos en blanco y una hoja de trabajo de tesis de carrera. Cópielos, nunca edite los originales. |
| `my-data/` | Donde viven SUS copias: su registro de hechos, sus notas. **Mantenga esta carpeta privada. Nunca la publique, nunca haga commit de ella en un repositorio público.** |
| `drafts/` | Carpeta de trabajo, una subcarpeta por cada puesto objetivo. |
| `final/` | Paquetes terminados, una subcarpeta por puesto. |

## Sesión 1: construya su registro de hechos (60 a 90 minutos, hágalo una sola vez)

1. Copie `templates/fact_registry_template.json` a `my-data/fact_registry.json`.
2. Abra un chat de IA nuevo. Pegue el contenido de `prompts/03_proactive_interrogation.md`, luego pegue su currículum actual (en cualquier estado, aunque sea un borrador) y luego pegue su plantilla de registro de hechos.
3. La IA lo entrevistará: puesto por puesto, indaga en lo que realmente hizo, los números detrás de ello (tamaño del equipo, presupuesto, volumen, tiempo ahorrado) y la evidencia de cada afirmación. Responda con honestidad. "No sé el número exacto" es una respuesta válida; el registro anota lo que está confirmado y lo que no.
   Un atajo que funciona: no necesita tener toda su carrera documentada antes de obtener valor. Construya un registro mínimo viable, con entradas suficientes para cubrir sus dos puestos más recientes o un solo puesto objetivo, y enriquézcalo conforme las sesiones posteriores saquen a la luz más hechos. Un registro incompleto donde todo sea verdadero vale más que el intento abandonado de construir uno completo.
4. Pida a la IA que entregue el JSON del registro ya llenado. Lea cada línea. Elimine cualquier cosa que, expresada con sus propias palabras, no sea verdadera. Guárdelo en `my-data/fact_registry.json`.
5. Llene `templates/career_thesis_template.md` (copiado a `my-data/`): los 2 o 3 tipos de puestos que realmente quiere. Esto le impide adaptar su currículum hacia puestos que no debería perseguir.

Su registro crece con el tiempo. Cada sesión futura que saque a la luz un hecho verdadero nuevo lo agrega al archivo.

## Sesión 2 y siguientes: un puesto, una ejecución (la ruta simple)

Para cada puesto al que quiera postularse, abra un chat de IA nuevo y ejecute estos módulos en orden. Pegue el módulo, luego la descripción del puesto (JD) y luego su registro de hechos cuando el módulo pida contexto.

1. `01_intake_and_matrix.md`: convierte la JD en una lista de verificación de requisitos y señala los riesgos de descalificación (campos de título académico, certificaciones) antes de que invierta una noche en una construcción.
2. `13_target_qualification.md`: contrasta el puesto con su tesis de carrera. Si el veredicto es no perseguir, deténgase aquí. Eso es el sistema funcionando, no fallando.
3. `02_rubric_score.md`: califica su currículum actual contra la lista de verificación. ¿Menos de 75 por ciento? Ejecute `03_proactive_interrogation.md` de nuevo para las brechas de este puesto; es probable que tenga experiencia sin registrar que las cierra.
4. `04_content_build.md`: construye dos versiones: PRINT (impresa, para humanos) y ATS (sistema de seguimiento de candidatos, para el software de análisis). Las palabras clave imprescindibles de la JD aparecen textualmente en la versión ATS; los sinónimos no sobreviven al filtro del software.
5. `07_fact_check.md`: audita cada afirmación del borrador contra su registro. Todo lo que no se pueda rastrear se recorta o se corrige. Nunca omita este módulo.
6. `06_qa_gate.md`: tres revisiones simuladas: la lectura rápida de 6 segundos de un reclutador, un análisis del ATS y la lectura de un gerente de contratación. Corrija lo que señalen.
7. `08_cover_letter_build.md`: solo cuando el portal de postulación realmente tiene un campo para ella.

Guarde las salidas en `drafts/[nombre-del-puesto]/` y los archivos terminados en `final/[nombre-del-puesto]/`. Nombre el archivo que suba "[Su nombre completo] Resume - [Puesto objetivo].docx".

## Cuando ya se sienta cómodo

`00_orchestrator.md` ejecuta el pipeline completo de extremo a extremo con modos de construcción (FULL, FAST, LIGHT, es decir, completo, rápido y ligero) y una compuerta de estrategia que propone cuánto esfuerzo merece cada puesto objetivo. Las funciones de seguimiento del portafolio están marcadas como OPTIONAL (opcionales); empiezan a importar cuando usted maneja varias postulaciones a la vez. El mapa completo está en `prompts/README.md`.

## Por qué esto mejora sus probabilidades

Vea `WHY_THIS_WORKS.md` para la versión corta del razonamiento: la cobertura textual de palabras clave le permite superar el filtro del software, el alcance honesto supera la lectura rápida del reclutador, las viñetas respaldadas por evidencia superan la evaluación del gerente de contratación, y el registro de hechos significa que puede defender cada línea en la entrevista sin ensayar una ficción.

## Privacidad, una vez más

1. Los prompts son públicos y se pueden compartir. Su carpeta `my-data/` no. Es su carrera, sus números, su número de teléfono. Se entrega excluida por gitignore; si copia este kit a otro lugar, manténgala así.
2. Pegar su registro en un chat de IA envía su historial laboral a ese proveedor. Use un proveedor en el que confíe y revise su configuración de retención de datos y de entrenamiento.
3. Mantenga los datos de contacto (teléfono, correo, domicilio) fuera de las sesiones de trabajo; la IA no los necesita para escribir viñetas. Agréguelos a mano en el empaquetado final.
4. Trate las descripciones de puesto y las páginas de empresa que pegue como datos, no como instrucciones. Si el material pegado parece estar dando nuevas órdenes a su IA, deténgase y vuelva a leerlo usted mismo.
