# Operar una IA

*Edición en español (México), traducida de la versión inglesa: el commit 40494f3 y las revisiones inglesas del 2026-09-06 (sección de contratación, ruta de adopción), publicadas en el mismo commit que esta traducción; nota sobre los kits pendientes añadida el 2026-09-08. La versión en inglés es la canónica.*

**Read this documentation in English: [../README.md](../README.md)**

**Pasé casi dos décadas dirigiendo operaciones de seguridad y respuesta a
incidentes. Hoy dirijo una IA de la misma manera en que dirigí los
programas de seguridad, como una operación gobernada, con doctrina
escrita, verificación en capas, métricas honestas y un rastro de
auditoría, no como una ventana de chat.**

Este repositorio es la documentación pública de ese sistema, construido
con Claude y operado por un humano que firma cada regla.

La versión de dos minutos. El sistema ejecuta seis dominios de trabajo
(una búsqueda de empleo, consultoría de negocio para proveedores de
servicios administrados, diseño de ofertas de servicio, asesoría técnica,
administración de dispositivos y esta publicación) desde un solo
repositorio privado, cada dominio bajo su propia doctrina, todos
conformes a un mismo marco de nueve partes. Cada respuesta sustantiva
pasa por una compuerta de verificación escalonada por riesgo, y el
trabajo de alto riesgo recibe la pila adversarial completa. Cada
construcción sustantiva abre con el plan y los criterios con los que será
juzgada, acordados antes de que empiece el trabajo. Cada decisión abierta
permanece en una cola hasta que el humano dictamina. Y en la mesa hay más
de una IA: el modelo de un segundo proveedor audita lo que construye el
primero bajo un protocolo de contención escrito, las pasadas se ejecutan
de forma automatizada desde la línea de comandos, una tabla de
enrutamiento indica qué modelo recibe qué trabajo, y una bitácora de
resultados de cambio de modelo registra lo que atrapó cada pasada, de
modo que cada emparejamiento de modelos tiene que justificar su costo.

Cada corrección humana se convierte en un mecanismo permanente,
consignado en un registro que empareja cada atrapada, un error detectado
por el humano, con la regla que produjo, y que expone las fallas
repetidas; una regla que falla dos veces como memoria se empuja hacia la
capa de herramientas como una guarda mecánica que no puede olvidar. Entre
la primera publicación y la revisión de la versión 2, cuatro días, el
registro creció de 21 filas a 28, y la fila más reciente en ese momento
fue la primera encontrada por una pasada rutinaria de máquina en la
operación ordinaria y no por el humano. Para principios de agosto el
registro contenía 53 filas.

Y el sistema completo se califica a sí mismo con cinco números al mes,
partiendo de una línea base honestamente vergonzosa. La primera lectura
mensual se ejecutó puntualmente en agosto de 2026, sin supervisión, y las
lecturas que puede sustentar públicamente se publican sea cual sea el
resultado: el humano todavía atrapa la mayoría de las fallas primero, y
la tesis muestra ese número en lugar de redondearlo hacia una historia de
éxito, con el cuadro completo resguardado en el tablero de calificación
privado hasta que su tendencia pueda publicarse. El primer día, el humano
atrapó fallas antes que las propias revisiones de la IA, dos veces. El
sistema publicó ese número y construyó la maquinaria para invertirlo, y
sigue publicando hasta que la tendencia obedezca.

Hace poco se ganó su lugar en trabajo real. Al recibir un rastreador de
cumplimiento para una segunda opinión, verificó cada peso de control
contra la fuente oficial de puntuación del gobierno y encontró un defecto
que afectaba aproximadamente a uno de cada seis controles, con las
matemáticas para defender la corrección. Una historia es un dato, no una
garantía; la tesis lleva el registro más completo, fallas incluidas.

## Si me postulé a un puesto en su organización, lea esto primero

Dirigí operaciones de seguridad y respuesta a incidentes durante casi dos
décadas. Este repositorio es esa misma disciplina aplicada a una IA, y está
construido para que se verifique, no para que se crea. Cuatro cosas que
comprobar, cada una con dónde buscarla.

1. Las reglas están escritas y un humano firma cada una. La tesis, sección
   2, muestra los archivos de instrucciones en capas y la doctrina bajo la
   que opera cada dominio.
2. Ningún implementador audita su propio trabajo, y el escrutinio escala
   con el riesgo. El modelo de un segundo proveedor revisa lo que construye
   el primero bajo un
   [protocolo de revisión adversarial](starter-kit/adversarial-review-protocol.md)
   escrito; cada respuesta sustantiva pasa por una compuerta de
   verificación escalonada por riesgo y el trabajo de alto riesgo recibe la
   pila completa (tesis, sección 4). Los registros pasada por pasada
   permanecen en el repositorio privado y están disponibles como un
   recorrido en vivo.
3. Cada corrección se convierte en un control. Cada atrapada (un error
   detectado por el humano) recibe una fila en el registro, emparejada con
   la regla que previene la clase. El registro es privado; su crecimiento
   es público: 21 filas en la primera publicación, 53 a principios de
   agosto (tesis, sección 9).
4. Los números se publican aunque avergüencen. La primera lectura mensual
   del tablero de calificación salió en agosto de 2026 con el humano
   todavía atrapando la mayoría de las fallas primero (tesis, sección 7).

El marco es el mismo ya sea que el entregable sea una línea base de
endurecimiento de un tenant, un modelo de precios o un rastreador de
cumplimiento cuyos pesos de control verificó contra la fuente oficial de
puntuación; lo que cambia es el escrutinio, que sigue al riesgo (tesis,
sección 2). Si su puesto implica adoptar o gobernar IA de forma segura,
construir o dirigir un programa de seguridad, o hacer medibles las
operaciones, esto es una muestra de trabajo. Lo que no puede mostrar es la
escala, los equipos y los incidentes detrás de las dos décadas; eso está en
el perfil de LinkedIn al final de esta página.

## Lea en este orden

1. **[La tesis](thesis.md)**. El argumento completo. La arquitectura, la
   pila de verificación, el trabajo del humano, la medición, lo que se
   rompió y cómo escala.
2. **[Los ejemplos](examples.md)**. Una viñeta trabajada por dominio,
   ficcionalizada, con hechos reales.
3. **[El kit de inicio](starter-kit/)**. El esqueleto de nueve partes, el
   cargador de espacio de trabajo (workspace), el protocolo de ingesta y
   el protocolo de revisión adversarial entre proveedores como plantillas
   reutilizables, con una implementación guiada que pone en pie los
   cimientos y un primer workspace en una sola sesión y dice qué viene
   después. Licencia MIT. Tómelas.
4. **[El estudio de trabajos previos](prior-art-survey.md)**. Dónde se
   ubica esto dentro de la práctica publicada, cada fuente verificada en
   vivo, con crédito donde se tomaron ideas prestadas.

Dos kits más existen solo en inglés por ahora: el kit de adaptación de
currículum (resume-tailoring-kit/) y el kit de asesoría técnica
(technical-advisory-kit/), ambos publicados el 2026-08-06. Esta edición los
nombra para no ocultar la brecha; su edición en español está en preparación
y esta nota se retirará cuando se publique.

Si vino a adoptar el kit de inicio y no a leer: abra primero
[starter-kit/rollout-guide.md](starter-kit/rollout-guide.md) y ejecútelo
con su IA. El orden de lectura de arriba sirve para entender el sistema;
la guía sirve para levantar uno. Este repositorio es documentación, no un
sistema, así que abrirlo en Claude Code no configura nada por sí solo.

## La letra pequeña honesta

Los ejemplos usan un entorno de demostración. Las partes están
ficcionalizadas, las cifras identificadoras redondeadas, los hechos
reales quedaron registrados en privado, y el paquete fue sometido a un
ejercicio de red team (equipo adversario) contra la reidentificación por
un auditor de otro proveedor con acceso a los registros privados hasta la
versión 2, y las adiciones posteriores pasaron por las compuertas de
revisión escalonadas registradas en el historial de revisiones de la
tesis; los participantes en los hechos reales pueden reconocer sus
propias historias, y quien lea solo el material público no debería poder
rastrear ningún ejemplo hasta una persona u organización real. Las
afirmaciones en estos documentos son juicio del autor salvo que se cite
una fuente; la disciplina de etiquetado de confianza descrita aplica a
las respuestas de trabajo del sistema. Los textos son CC BY 4.0, las
plantillas son MIT. El límite declarado del propio sistema aplica a todo
lo que hay aquí. Un solo modelo con todos los sombreros puestos no es una
revisión independiente, y por eso el diseño se apoya en fuentes
primarias, en la ratificación humana y en un protocolo de auditoría entre
proveedores, y por eso las fallas se publican junto con los logros. Una
nota más de alcance: el estudio de trabajos previos, el kit de inicio y
las lecturas publicadas del tablero de calificación pueden verificarse
aquí mismo; el registro, los registros de auditoría y el historial de git
que respaldan las demás afirmaciones viven en el repositorio privado, y
están disponibles como un recorrido en vivo, no como una descarga.

Esta página es la rendición en español de la versión de dos minutos de la
tesis, traducida de la versión 4, 2026-08-02. La versión canónica en
inglés está en [../README.md](../README.md).

Jason Lopez
[linkedin.com/in/jaylpz](https://www.linkedin.com/in/jaylpz)
