# Protocolo de revisión adversarial (plantilla)

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

El valor de una segunda IA es máximo cuando se le permite atacar y se le
prohíbe gobernar. Esta plantilla es agnóstica al modelo: solo asume que
usted cuenta con un modelo autor y un modelo auditor de proveedores
distintos, cada uno accesible en alguna forma automatizable (una interfaz
de línea de comandos (CLI), una API o, en el peor de los casos, un copiado
y pegado disciplinado). La separación es el control; las herramientas son
una conveniencia.

## Las ocho reglas

1. **Una sola carpeta de intercambio.** La revisión completa vive en una
   sola carpeta de trabajo dedicada. Todos los demás archivos de su
   repositorio son insumo de solo lectura para el intercambio, citados
   pero nunca editados por él.
2. **La divulgación es una decisión.** Lo que el modelo externo puede
   leer lo dictamina explícitamente el humano, en cada encargo, nunca
   como un valor por defecto. El material con datos de clientes o datos
   personales entra a un intercambio solo por decisión nombrada, asentada
   en el registro.
3. **Proveedores distintos, sillas distintas.** El modelo que fue autor
   del trabajo nunca lo audita. Cuando se ratifican cambios, un modelo
   implementa y el otro audita los diffs, la comparación línea por línea,
   contra exactamente lo que se acordó.
4. **Las rondas tienen tope y son secuenciales.** Un debate que puede
   alargarse para siempre erosionará las protecciones por repetición.
   Fije el tope antes de la ronda uno (de tres a cinco es lo típico). Dos
   tipos de ronda tienen condiciones de éxito opuestas, y confundirlos
   rompe el protocolo: una ronda de hallazgos que regresa vacía temprano
   en el intercambio es sospechosa, regístrela y trátela como una lectura
   superficial y no como un dictamen limpio; una ronda de verificación
   que confirma presente cada corrección previa mediante cita exacta y no
   plantea nada nuevo es la condición de éxito que termina el
   intercambio.
5. **Las correcciones se verifican con citas exactas.** Cada ronda vuelve
   a verificar las correcciones de la ronda anterior citando el archivo
   actual, y el conteo de hallazgos solo baja cuando una corrección está
   verificablemente presente. Un parche que no puede mostrar su propio
   texto en el archivo no ocurrió; registre la afirmación falsa en la
   procedencia en lugar de hacerla desaparecer con otra redacción.
6. **Ninguna convergencia puede debilitar una protección.** Un punto
   medio entre dos modelos que afloja una regla de honestidad o la
   autoridad del humano no es convergencia, es erosión. Las protecciones
   solo se fortalecen a través de un intercambio.
7. **La salida es un menú de decisiones.** El intercambio produce
   hallazgos y opciones para que el humano dictamine. Nada en él se
   ejecuta por sí solo, y nada se convierte en una regla de su sistema
   sin la ratificación explícita del humano.
8. **La procedencia se conserva.** El prompt y la respuesta de cada ronda
   se persisten en la carpeta de intercambio. El registro de quién
   encontró qué, quién corrigió qué y quién lo verificó ES el rastro de
   auditoría del entregable.

## La ejecución, paso a paso

1. Congele el conjunto de artefactos bajo revisión y liste los archivos
   en alcance.
2. Escriba el encargo del auditor: la lista de artefactos, las
   afirmaciones que hace el trabajo y la instrucción de refutar, no de
   resumir. Nombre el formato de los hallazgos (archivo, cita, por qué
   está mal, severidad).
3. Ejecute la ronda del auditor. Persista el prompt y la respuesta en la
   carpeta de intercambio.
4. Haga el triaje de los hallazgos con el humano: aceptar, disputar con
   evidencia o dictaminar fuera de alcance. Las disputas llevan la
   evidencia, no solo el desacuerdo.
5. Implemente las correcciones aceptadas (con el modelo autor) y luego
   ejecute la siguiente ronda del auditor para verificar cada corrección
   mediante cita exacta, además de buscar hallazgos nuevos.
6. Repita dentro del tope de rondas hasta lograr una ronda de
   verificación limpia, y entonces registre el veredicto: acordado, o no
   acordado con los residuales nombrados.
7. Registre lo que el auditor atrapó y el autor pasó por alto. Un
   emparejamiento que no atrapa nada a lo largo de los ciclos se baja de categoría;
   uno que justifica su costo se convierte en su opción por defecto para esa
   clase de trabajo.

## Llevar una bitácora de resultados de cambio de modelo

Una sola tabla, donde solo se agrega al final: fecha, trabajo, modelo
autor, modelo auditor, qué atrapó el auditor que nadie más atrapó. Esta
es la evidencia que decide qué modelo ocupa qué silla para qué trabajo, y
es la respuesta honesta a la pregunta de si el segundo modelo vale lo que
cuesta, la que ninguna página de proveedor le dará.
