# El esqueleto de nueve partes (plantilla)

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Todo dominio de trabajo gestionado por IA (una búsqueda de empleo, una
función de negocio, una práctica de asesoría, un programa de cumplimiento)
se construye a partir de este marco. Complete cada parte para su dominio.
Las desviaciones están permitidas y se alientan cuando su contexto es
genuinamente distinto, pero deben ser NOMBRADAS con una razón, nunca
omitidas en silencio. La palabra "parcialmente" nunca puede pasar en
silencio.

## 1. Lentes

Las perspectivas que la IA aplica MIENTRAS construye el trabajo, no solo
al revisarlo después. Nombre de tres a cinco que se ajusten a su dominio.

> Formas de ejemplo: el lente de un comprador, el lente de un arquitecto de
> seguridad, un lente de cumplimiento, un lente de experiencia del lector.

Sus lentes:
- ...

## 2. Personas

Para quién es realmente el trabajo, puesto por escrito, de modo que todo
se moldee para un lector real y no para uno genérico.

Sus personas:
- ...

## 3. Rúbrica

Cómo se califica el trabajo antes de entregarse. Los criterios para una
pieza de trabajo dada se acuerdan antes de que inicie la construcción,
nunca se descubren al momento de calificar, de modo que la vara se fija
por adelantado en lugar de escribirse después de ver el resultado. La
calificación y las debilidades encontradas se presentan JUNTO CON el
trabajo, nunca se absorben en silencio dentro de él, y el trabajo ya
entregado recibe crítica retrospectiva con una cadencia. Una revisión que
no produce hallazgos está incompleta, no es un elogio.

Sus dimensiones (con una escala de veredicto, p. ej. sólido / sólido con
salvedades / defectuoso):
- ...

## 4. Controles de error

Seis mínimos. Todo número que impulsa una decisión lleva su valor, fecha
y fuente, marcado como dato real o como estimación. Nada que salga omite
una verificación final previa al envío. Toda sesión comienza conciliando
el estado actual con el último estado registrado. Un conjunto de cambios entregado
contiene solo los cambios propios de ese trabajo, verificado contra su
afirmación antes de liberarse. La entrega se concilia con la petición
original detallada punto por punto, de modo que nada de lo pedido se
descarta en silencio y nada de lo agregado se olvida en silencio. Y los
registros bajo corrección permanecen auditables: los identificadores se
agregan al final, nunca se renumeran; los hallazgos resueltos se marcan
como resueltos en su lugar, nunca se eliminan; y una afirmación de éxito
se prueba reabriendo el artefacto y revisando la salida observada, nunca
se asevera a partir de la edición.

Sus adiciones o desviaciones nombradas:
- ...

## 5. Ciclo de aprendizaje

Cuando una corrección o una pieza terminada le enseña algo, eso se
escribe en el archivo correcto para que la siguiente pieza de trabajo sea
mejor. Cada lección tiene un destino nombrado, y también lo tiene cada
artefacto: antes de escribir algo nuevo, confirme dónde aterriza. Algunos
destinos viven fuera del espacio de trabajo (workspace), como una bandeja
de entrada entre dominios o un registro compartido, de modo que nada
aprendido en algún lugar se olvide en todas partes. Dos adiciones se
ganaron por el camino difícil. La investigación externa nunca aterriza
como un resumen aislado: ánclela a los marcos que rigen su dominio,
declare qué no logran capturar esos marcos y vincúlela con lo que usted ya
sabe, porque los hechos aislados no se convierten en competencia. Y las
lecciones que nadie nombra en el momento se acumulan en silencio dentro
del trabajo de larga duración, así que combine el enrutamiento por lección
descrito arriba con un barrido al cierre: nada se cierra hasta que sus
archivos de trabajo se barren en busca de lecciones sin cosechar y cada
una recibe un dictamen que la incorpora a la doctrina o la descarta.

Su enrutamiento (un hecho va a..., una regla reutilizable va a..., una
corrección de proceso va a...):
- ...

## 6. Límite declarado

Una oración honesta sobre lo que este sistema no puede hacer. La forma
estándar: un solo modelo usando todos los sombreros no es revisión
independiente; los datos reales y la corrección del humano son las
verificaciones más fuertes. Escriba el suyo. Es la oración que hace
creíble todo lo demás.

Su límite declarado:
- ...

## 7. Compuerta de verificación

Cualquier cosa que dependa de un proveedor, una versión, un precio o del
tiempo se verifica contra una fuente viva antes de declararse, nunca
desde la memoria del modelo. Las afirmaciones llevan una etiqueta de
confianza: hecho establecido, práctica de consenso o juicio propio. El
trabajo de alto riesgo recibe una pasada adversarial separada, construida
para refutarlo. La compuerta cubre enfoques además de hechos: antes de
inventar un mecanismo novedoso, investigue cómo la práctica establecida ya
lo resuelve y dé crédito a lo que tome prestado. Las mismas compuertas
aplican a los cambios a este sistema mismo. La compuerta también mira
hacia adentro: cualquier artefacto entregado al sistema se inventaría
estructuralmente y se lee completo antes de extraer conclusiones de él;
una lectura truncada o acotada por palabras clave es una condición de
alto, nunca se reporta como análisis; y cuando los datos de alguien
contradicen lo que esa persona dijo, ganan los datos y la discrepancia se
convierte en un hallazgo.

Sus detonantes de alto riesgo (lo que obliga a la pasada adversarial en
su dominio):
- ...

## 8. Tablero de trabajo

Si un dominio lleva más de un hilo abierto, mantiene un archivo de
tablero permanente que la sesión lee primero: qué está activo ahora (en
orden), qué está en espera de usted, qué está en espera de otros, qué
está bloqueado y por qué cosa, qué está estacionado, qué está terminado.
Dos reglas duras lo hacen real. El tablero se actualiza en el mismo
commit que cualquier trabajo que lo cambie, porque un trabajo que no está
en el tablero significa que el tablero estaba equivocado. Y cada fila que
espera de un humano declara CUÁNDO actuar y QUÉ SUCEDE DESPUÉS, porque un
punto de decisión sin su secuencia es una pila, no un plan.

Su tablero (o una desviación nombrada si este dominio es genuinamente de
un solo hilo):
- ...

## 9. Estándar por clase de documento

Cualquier tipo de documento que este dominio producirá más de una vez
(paquetes para clientes, reportes, guías, especificaciones) recibe un
estándar escrito a nivel de clase ANTES de que exista la segunda
instancia: qué debe lograr una instancia completa y cómo se nombran las
instancias. La calidad se vuelve una propiedad de la clase, no de la
instancia que haya recibido más atención. Las convenciones que ya existen
y funcionan (bitácoras fechadas, registros numerados) quedan como los
estándares de sus clases; esta parte no las reacondiciona, atrapa
temprano a la siguiente clase.

Sus clases de documento que se repiten y dónde vive el estándar de cada
clase:
- ...

Una nota de mantenimiento que se ganó su lugar aquí: cuando agregue una
parte a este esqueleto, actualice en el mismo cambio cada lugar que
declara el número de partes. De lo contrario, el conteo y la lista VAN a
desfasarse; en el sistema del que proviene esta plantilla, se desfasaron
tres veces antes de que la reparación se moviera al momento del cambio.
