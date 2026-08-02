# Operar una IA

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

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

Esta es la traducción a términos de contratación. Este repositorio es un
programa de seguridad aplicado a la IA. Doctrina escrita y gobernanza.
Controles en capas de distintos tipos, diseñados para que ninguna falla
individual sea silenciosa. Segregación de funciones en la revisión entre
proveedores, donde ningún implementador audita su propio trabajo.
Resultados medibles con líneas base honestamente vergonzosas, publicadas
a propósito. Un protocolo de auditoría entre proveedores. Un manejo de
fallas documentado que convierte cada incidente en un control. Esa es la
misma disciplina que he ejercido en operaciones de seguridad y respuesta
a incidentes durante casi dos décadas, apuntada ahora a una nueva clase
de sistema. El trabajo que gobierna abarca implementación técnica, marcos
de negocio y ejecución de cumplimiento, y las mismas compuertas están
construidas para gobernar el diseño técnico. Si su puesto implica adoptar
IA de forma segura, construir o dirigir programas de seguridad, o hacer
medibles las operaciones, este repositorio es una muestra de trabajo, no
una afirmación.

## Lea en este orden

1. **[La tesis](thesis.md)**. El argumento completo. La arquitectura, la
   pila de verificación, el trabajo del humano, la medición, lo que se
   rompió y cómo escala.
2. **[Los ejemplos](examples.md)**. Una viñeta trabajada por dominio,
   ficcionalizada, con hechos reales.
3. **[El kit de inicio](starter-kit/)**. El esqueleto de nueve partes, el
   cargador de espacio de trabajo (workspace), el protocolo de ingesta y
   el protocolo de revisión adversarial entre proveedores como plantillas
   reutilizables, con una implementación guiada que pone en pie el marco
   en una sola sesión. Licencia MIT. Tómelas.
4. **[El estudio de trabajos previos](prior-art-survey.md)**. Dónde se
   ubica esto dentro de la práctica publicada, cada fuente verificada en
   vivo, con crédito donde se tomaron ideas prestadas.

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
