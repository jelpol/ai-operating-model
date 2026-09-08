# Notas para cargar en el sistema de seguimiento de candidatos (ATS): referencia rápida

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo:** Documento de referencia, no un módulo
**Propósito:** Lista de verificación justo a tiempo para manejar las particularidades comunes al cargar en un ATS. Léala inmediatamente antes de enviar cualquier postulación.

**Nota de campo:** Algunos ejemplos de abajo usan puestos de ciberseguridad y un perfil educativo sin título universitario concluido; adapte los detalles a su propio campo e historial. La estructura de la guía de acción es el producto.

## Use esto cuando
- Está a punto de cargar la versión ATS de un currículum en el portal de postulación de una empresa
- El portal pide campos que no corresponden claramente con su currículum
- Sospecha que el análisis automático salió mal después de la carga

---

## Guía de acción para preguntas eliminatorias

Las preguntas eliminatorias son la principal causa de rechazo de las postulaciones en frío. Un rechazo automático se dispara antes de que un humano vea siquiera el currículum. Maneje cada campo eliminatorio con deliberación.

**a) La pregunta del título universitario.** Responda con la verdad. Si no tiene el título, la respuesta es No. Nunca lo tergiverse. Una afirmación falsa de título es una falla en la verificación de antecedentes y es peor que cualquier rechazo.

**b) Evalúe la descripción del puesto (JD) ANTES de construir.** Si la JD dice "Se requiere licenciatura" SIN lenguaje de "o experiencia equivalente" y usted carece del título, ese es un puesto objetivo con riesgo de eliminación. Señálelo en el contexto de postulación del Módulo 01 para que decida invertir (o no) con los ojos abiertos.

**c) Campos de texto libre y de "otra educación".** Donde el formulario ofrezca un campo de texto libre o de "otra educación", use una declaración de equivalencia de una línea construida a partir de su registro de hechos, con este patrón: "[X]+ años de experiencia en [campo], incluidos [puestos sénior desempeñados], certificaciones vigentes, [cursos relevantes]."

**d) Registre los rechazos automáticos por título que sospeche.** OPCIONAL; se vuelve útil cuando usted maneja varias postulaciones a la vez. Toda postulación que se sospeche que fue rechazada automáticamente por una pregunta eliminatoria sobre el título se registra en sus notas de sesión (my-data/). Esos empleadores pierden prioridad en la selección futura de puestos objetivo; no tiene caso alimentar de nuevo el mismo filtro.

**e) Menús desplegables de años de experiencia.** Responda con la carrera completa. No se quede corto respondiendo desde un solo puesto o título.

**f) Campos de salario.** Elija UNA postura ANTES de cualquier entrevista inicial y manténgala. Nunca escriba "negociable". Prefiera dejar el campo en blanco donde se permita; donde sea obligatorio, ingrese el tope del rango investigado.

**g) Campos de habilitación de seguridad (clearance) o credencial destacada.** [Opcional: una línea para una habilitación de seguridad vigente o una certificación destacada, si la tiene.] Declare exactamente lo que tiene, nada más específico. Nunca afirme tener un nivel o una credencial que no estén confirmados en su registro de hechos.

---

## Campos de educación

Esta sección importa más si su educación consiste en cursos y no en un título concluido. Fije su presentación de la educación una sola vez en prompts/principles.md y reutilícela en todas partes:

- **Línea de educación PRINT (versión para impresión):** una línea de cursos como "[Universidad], cursos de un programa de B.S. en [Campo] (en pausa por compromisos profesionales)". Ninguna afirmación de título, nunca.
- **Línea de educación del archivo ATS:** "[Universidad] - cursos de nivel universitario en [Campo] (en pausa por compromisos profesionales)". Razón: los analizadores (parsers) de los portales de la clase Greenhouse (portal ATS), Oracle (proveedor de software empresarial), Workday (portal ATS) y Paycor (plataforma de RR. HH.) extraen el nivel de título del token "B.S." en cualquier parte de la entrada de educación e ignoran los paréntesis, autocompletando una licenciatura concluida que contradice una respuesta veraz sobre el título en la misma postulación. Eliminar por completo el token de título es la única redacción que derrota al analizador; la razón "(en pausa por compromisos profesionales)" se queda para los lectores humanos. La revisión manual de la tarjeta de educación descrita abajo sigue siendo la verdadera compuerta.
- **Formularios ATS que exigen el historial completo:** en ellos puede listar, con exactitud, cada institución a la que asistió. El historial completo existe solo donde el formulario lo exige.
- **Menús desplegables de "Nivel máximo de estudios concluido":** "Some college" (estudios universitarios sin título) o la opción veraz más cercana. Nunca seleccione un nivel de título que no haya obtenido.
- **Campos de año de graduación:** para entradas de solo cursos, ingrese el año más reciente de actividad en los cursos (los motores ATS exigen un año).
- **Revise siempre la tarjeta de educación generada automáticamente** después de la carga y corrija cualquier título autocompletado antes de enviar; es un requisito de integridad, no algo opcional.

---

## Árbol de decisión ATS frente a PRINT

- Carga en portal = docx ATS (o PDF donde el portal lo prefiera: Greenhouse, Lever (portal ATS))
- Correo a un humano = PDF PRINT
- Un reclutador pide "su currículum" sin portal = PDF PRINT
- Entrega en la entrevista = PDF PRINT, impreso

El archivo que realmente se carga o se envía por correo usa el nombre de archivo para el envío ("[Su nombre completo] Resume - [Puesto objetivo]") según el Módulo 11, nunca el nombre interno de archivo de trabajo "[SuNombre]-...".

---

## Portales ATS comunes y sus particularidades

### Workday
- **Formato de archivo:** docx preferido sobre PDF (el análisis es mejor)
- **Trampa de Quick Apply (postulación rápida):** autocompleta los campos con datos incorrectos. Revise cada campo antes de enviar
- **Conteo de páginas:** Se procesan de forma confiable 4 páginas; algunas configuraciones cortan el contenido después de la página 3
- **Año de educación:** Workday exige un año de graduación. Para solo cursos, ingrese el año más reciente de actividad
- **Campo de habilidades:** Workday pondera mucho este campo. Pegue de forma literal el contenido de sus "Competencias clave" (Core Competencies)
- **Carta de presentación:** normalmente es un campo aparte; no la pegue dentro del currículum

### Árbol de decisión para entregar la carta de presentación (algunos sitios no permiten adjuntarla)
1. **Existe un campo de adjunto:** adjunte el PDF de la carta.
2. **Existe un cuadro de texto (carta de presentación / información adicional / por qué le interesa):** pegue el cuerpo de la carta como texto plano (solo el párrafo de apertura si el cuadro es de la clase "por qué le interesa"; ese cuadro prevalece sobre un adjunto).
3. **NO hay campo de ningún tipo:** NO fuerce la carta (nunca la incruste en el archivo del currículum, nunca la meta en una pregunta no relacionada). La carta se construye y se empaqueta de todos modos; se convierte en material para el contacto con reclutadores y el correo de seguimiento. Anote en el manifiesto del paquete, al momento del envío, que no había campo.

### Greenhouse
- **Formato de archivo:** PDF aceptable aquí (conserva mejor el formato)
- **Cuadro de texto "por qué le interesa":** si existe, pegue el párrafo de apertura de su carta de presentación; este cuadro prevalece sobre la carta adjunta (vea COLD PORTAL MODE, modo de portal en frío, en el Módulo 08)
- **Currículums de varias columnas:** Greenhouse analiza con más confiabilidad una sola columna; la versión ATS con diseño de una sola columna es crítica
- **Preguntas personalizadas:** los reclutadores sí las leen. No las omita; responda con brevedad

### Lever
- **Formato de archivo:** PDF preferido
- **Análisis del currículum:** elimina el formato al mostrarlo. La estructura importa menos, el contenido importa más
- **Campo de carta de presentación:** normalmente un solo cuadro de texto; pegue la carta como texto plano

### iCIMS (portal ATS)
- **ATS más antiguo, análisis más frágil**
- **Formato:** use la versión ATS con el formato más simple
- **Rayas (em dashes):** iCIMS a veces las muestra como signos de interrogación. Use guiones normales (el Principio #14 prohíbe las rayas de todos modos)
- **Encabezados y pies de página:** se eliminan al analizar. Nunca ponga ahí la información de contacto
- **Manejo de fechas:** iCIMS es quisquilloso. Use el formato "MMM YYYY" de forma consistente ("Feb 2025", no "February 2025")

### Taleo (portal ATS)
- **El peor analizador entre los principales.** Asuma que el análisis destrozará cualquier cosa que no sea trivial
- **Gana el archivo más simple:** docx ATS, una sola columna, cero decoración
- **Espere reingresar campos a mano:** reserve tiempo para volver a teclear títulos, fechas y educación después de la carga; verifique cada campo analizado

### SuccessFactors (plataforma de RR. HH.)
- **Analizador muy literal.** Mantenga el formato al mínimo
- **Verifique con cuidado la vista previa analizada** antes de enviar; tomará lo que analizó, no lo que usted cargó

### SmartRecruiters (portal ATS)
- Analizador moderno, en general se comporta bien; el docx ATS estándar funciona
- Aun así, revise la vista previa y verifique cada campo autocompletado

### Ashby (portal ATS)
- **Común en empresas del sector de IA**; espérelo en esos puestos objetivo
- Analizador limpio; las preguntas personalizadas son prominentes y las leen humanos; respóndalas con deliberación

### Portal de ADP (proveedor de nómina y RR. HH.)
- Portal de suite de RR. HH., cargado de formularios; el análisis es secundario frente a los formularios
- Espere ingresar la mayoría de los datos a mano; el currículum se adjunta como documento

### LinkedIn Easy Apply (postulación sencilla de LinkedIn)
- **Verifique SIEMPRE que llegue la confirmación del envío.** Una postulación real produjo alguna vez solo un aviso de error, y su estado nunca pudo verificarse después
- Tome captura de pantalla o guarde la confirmación de cada envío por Easy Apply; regístrela en sus notas de sesión
- Si no aparece confirmación, trate la postulación como NO enviada y dé seguimiento

### Postulaciones genéricas por correo electrónico
- Use la versión PRINT, no la ATS; la lee un humano
- Adjunte como PDF (conserva el formato), con el nombre de archivo para el envío: "[Su nombre completo] Resume - [Puesto objetivo].pdf"

---

## Reglas universales para cualquier ATS

1. **Revise siempre la vista previa después de la carga.** La mayoría de los portales ATS le muestran lo que analizaron. Corrija cualquier cosa que se vea mal antes de enviar.

2. **No confíe en el autocompletado.** Los motores ATS adivinan sus títulos de puesto, fechas y educación. Verifique cada campo.

3. **Regla del título en el titular.** Reflejar el título del puesto de la JD aplica ÚNICAMENTE a la línea HEADLINE (titular) debajo del bloque de contacto y al encuadre del resumen. Si la JD dice "Director de Gestión de Identidades y Accesos" y el titular dice "Director de Operaciones de IAM", ajuste el titular a la redacción exacta de la JD donde sea veraz. Las líneas de título de puesto reales en la sección de Experiencia NUNCA se retitulan; los títulos reales se quedan y el contenido cierra la brecha (bloqueo title_to_content_bridge, el puente entre título y contenido, Principio #10).

4. **Verificación de densidad de palabras clave.** Asegúrese de que las palabras clave imprescindibles de la JD aparezcan al menos 2 veces. Use la verificación de densidad de palabras clave del Módulo 02 antes de cargar.

5. **Consistencia del formato de fechas.** Use el mismo formato en todo el documento: "Feb 2025 - Present"; no lo mezcle con "February 2025 - Present" en otra parte.

6. **Manejo del año de educación.** Si su educación es "Cursos" y no un título concluido, ingrese el año más reciente de los cursos. Los motores ATS exigen un año para las entradas de educación. (Vea la sección Campos de educación arriba para la guía completa.)

7. **Referencias.** Nunca incluya referencias en el currículum. Si la postulación pide referencias, entréguelas por separado cuando se las soliciten.

8. **Campo de expectativa salarial.** Elija UNA postura antes de cualquier entrevista inicial. Nunca escriba "negociable". Déjelo en blanco donde el campo lo permita; donde sea obligatorio, ingrese el tope del rango investigado. No improvise una cifra a mitad de la postulación.

9. **Sección de diversidad/EEO.** Siempre opcional. Es su decisión.

---

## Lista de verificación previa al envío

Antes de hacer clic en enviar en cualquier postulación:

- [ ] Versión ATS del currículum cargada (no la PRINT), con el nombre de archivo para el envío según el Módulo 11
- [ ] Carta de presentación cargada o pegada según la decisión de colocación del Módulo 08 (campo aparte, no incrustada)
- [ ] Cada campo autocompletado verificado
- [ ] El título del puesto en el HEADLINE coincide con el vocabulario de la JD (donde sea veraz); los títulos de Experiencia intactos
- [ ] Pregunta del título universitario respondida con la verdad; declaración de equivalencia usada donde exista un campo de texto libre
- [ ] Campos de años de experiencia respondidos con la carrera completa
- [ ] Campo de habilitación de seguridad/credencial (si aplica): declare exactamente lo que tiene, nada más
- [ ] Campo de salario manejado según la única postura elegida de antemano
- [ ] URL de LinkedIn proporcionada y vigente
- [ ] Todas las preguntas personalizadas respondidas (no las omita)
- [ ] Sección de diversidad/EEO completada si así lo decide
- [ ] Personalización para el gerente de contratación en la carta de presentación (si se conoce el nombre)
- [ ] Confirmación del envío capturada (captura de pantalla o correo guardado; obligatorio para LinkedIn Easy Apply)
- [ ] Marca de tiempo del envío de la postulación capturada en sus notas de sesión

---

## Notas posteriores al envío (captúrelas en sus notas de sesión, my-data/)

Para cada postulación, registre:
- Fecha de envío
- Portal usado
- Nombre del reclutador o del gerente de contratación (si se conoce)
- ID de la postulación o número de confirmación (más la confirmación guardada en el caso de Easy Apply)
- Riesgos de eliminación sospechados (título, credencial) para poder interpretar los resultados después
- Notas sobre las particularidades del portal encontradas (para que las postulaciones futuras eviten la fricción)

Esto construye un historial de postulaciones consultable que informa las decisiones de adaptación futuras y la lista de empleadores despriorizados por rechazo automático de título. OPCIONAL; se vuelve útil cuando usted maneja varias postulaciones a la vez.

---

## Cuándo revisar este documento

Actualícelo cuando:
- Un portal ATS específico muestre una nueva particularidad que valga la pena rastrear
- Encuentre un problema de análisis que aún no esté documentado
- Un nuevo motor ATS se vuelva relevante para una familia de puestos objetivo
- Un envío exitoso revele un consejo no obvio específico del portal
- Un patrón sospechado de rechazo automático eliminatorio se confirme o se refute
