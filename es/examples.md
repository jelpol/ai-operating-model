# El sistema en acción: los dominios y los momentos que los pusieron a prueba

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Documento complementario de "Operar una IA". Jason Lopez. Versión 3, 2026-08-02,
derivado de la versión 4 de la tesis. La estructura consta de seis viñetas de
dominio, una por cada dominio de trabajo, retomadas de la versión 2 con una
redacción de privacidad afinada, seguidas de tres casos de estudio del
registro reciente que atraviesan varios dominios.

La misma convención que la tesis. Estos son eventos reales y registrados,
presentados como un entorno de demostración. Las partes están ficcionalizadas,
las cifras identificadoras están redondeadas, y los nombres de máquinas y
productos están difuminados donde podrían identificar a alguien o algo que no
sea yo. El conjunto fue sometido a un ejercicio de red team de reidentificación
por un auditor de otro proveedor con acceso a los registros privados hasta la
versión 2, y las adiciones posteriores pasaron por las compuertas de revisión
escalonadas registradas en el historial de revisiones de la tesis; el residuo
honesto es que las personas que participaron en los
eventos subyacentes pueden reconocer sus propias historias, y que quien lea
únicamente este material público no debería poder rastrear ningún ejemplo hasta
una persona u organización real. Los registros subyacentes viven en el
repositorio privado con
fechas y commits adjuntos.

## El espacio de trabajo (workspace) de búsqueda de empleo

Este es el dominio más estricto del sistema. Toda afirmación destinada a un
currículum debe rastrearse hasta una entrada del registro de hechos con
procedencia, es decir, un registro de cuándo la confirmé y en qué palabras.
Cuando la IA redacta una viñeta con lenguaje que yo no he confirmado, la
afirmación se marca y se presenta, nunca se envía en silencio y nunca se
descarta en silencio. Las decisiones de encuadre bloqueadas, la redacción
honesta acordada para los alcances sensibles, pueden ampliarse pero nunca
relajarse. Y un paquete terminado no puede enviarse hasta que una verificación
de múltiples pasadas genera el PDF real, extrae el texto de vuelta y comprueba
que tanto el formato como el contenido sobrevivieron. La lección que construyó
todo esto es simple. Un currículum que no puede sobrevivir un
contrainterrogatorio es peor que no tener currículum.

## El espacio de trabajo del jefe de gabinete

La IA mantiene un rastreador vivo de los asuntos de negocio abiertos del
trabajo de consultoría, conciliado en cada sesión con los sistemas vivos del
negocio. El mejor ejemplo de la disciplina es
una falla que atrapó en sus propios archivos. Una instrucción de carga
permanente seguía describiendo un evento como la máxima prioridad activa casi
dos semanas después de que el evento había ocurrido y cerrado. Un agente de
auditoría con contexto aislado la atrapó, porque la
regla aquí es que los archivos de estado actual nunca pueden cargar historia,
y la historia nunca puede hacerse pasar por estado actual. La corrección tomó
un minuto. El punto es que algo estaba cazando el problema.

## El espacio de trabajo de ofertas

El trabajo de precios y alcance corre sobre un libro mayor donde cada cifra que
impulsa una decisión registra su valor, su fecha, su fuente y si es un dato
real o una estimación. La regla vigente es que una estimación nunca aparece en
nada dirigido al cliente disfrazada de número validado. Antes de que cualquier
documento salga del edificio pasa una verificación previa al envío, y si algún
insumo sigue siendo una estimación, el documento se queda interno hasta que
exista el número real. Un número tiene fecha y fuente, o no se envía.

La corrida de facturación mensual muestra la misma disciplina desde otro
ángulo. Las tarifas viven en una configuración con dos lados declarados, lo que
cuestan los ingenieros y lo que se les factura a los clientes, y cada tarifa
lleva un estatus, real o requerida. Una tarifa requerida nunca se inventa. Se
muestra como una celda marcada y una pregunta numerada, y cada respuesta se
registra con quién la dio y cuándo, de modo que la misma pregunta nunca tiene
que hacerse dos veces y la lista de preguntas se reduce mes con mes. Preguntar
al humano es aquí un flujo de trabajo diseñado, no un modo de falla. Y cuando
pregunté si las matemáticas estaban bien, el sistema no releyó su propio libro
de cálculo. Recalculó cada cifra desde los datos fuente en bruto aplicando las
reglas desde cero, buscó entradas duplicadas y solo entonces dijo que sí, con
los riesgos restantes nombrados, incluida la única cosa que ningún recálculo
puede ver, las horas que nunca se registraron.

## El espacio de trabajo del asesor

Las preguntas técnicas pasan por una compuerta escalonada antes de que la
respuesta me llegue. Una consulta factual sencilla necesita una fuente
de autoridad y una etiqueta de confianza. Cualquier cosa que sea un juicio,
toque producción o cargue peso de seguridad recibe una segunda pasada
adversarial cuyo único trabajo es refutar el borrador. Un registro de
calibración rastrea en qué dominios soy experto, donde la IA valida a nivel de
par y nunca explica fundamentos, y cuáles estoy aprendiendo deliberadamente,
donde enseña. La misma pregunta recibe una forma de respuesta distinta según
quién la hace, y el sistema sabe quién soy.

## El espacio de trabajo de dispositivos

Un archivo de configuración canónico y un manifiesto de herramientas definen
cómo debe verse cada máquina desde la que trabajo. Cuando una máquina quedó
rezagada respecto del estándar, una auditoría estampó su registro como
rezagado y predijo qué faltaría, incluido un stub que se hace pasar por un
runtime real. La siguiente sesión en esa máquina corrió la verificación,
encontró las brechas predichas, instaló las herramientas con mi aprobación,
sincronizó la configuración y reemplazó el sello con un registro fechado. Las
máquinas registradas se conciliaron al mismo estándar declarado, y la
intención es que cualquier dispositivo nuevo recorra la misma verificación
hasta el mismo estado declarado, sean cuantos sean, porque el estándar está
escrito para la flota y no para los dispositivos que casualmente existían
primero. Mantener todo esto verdadero es ahora el trabajo de la verificación,
que corre cuando una máquina vuelve a trabajar, y no una tarea de memoria, con
el límite honesto de que una máquina que nadie abre es una máquina que nadie
ha verificado.

El control más nuevo de este dominio no nació aquí. Una regla sobre mantener
cada conjunto de cambios acotado a su propio trabajo falló dos veces como
regla recordada, así que se reconstruyó como un hook de preejecución que
bloquea mecánicamente la clase de comando riesgosa antes de que corra, y la
copia canónica vive en el estándar de dispositivos, de modo que cada máquina
hereda la salvaguarda igual que hereda el archivo de configuración. Un control
que se graduó de la memoria a la maquinaria es exactamente lo que este espacio
de trabajo existe para distribuir.

## El espacio de trabajo de publicación

El espacio de trabajo donde se prepara este mismo documento aplica las mismas
reglas sobre sí mismo, y su mejor ejemplo es un casi accidente. Un borrador
fuertemente revisado de la tesis pública estuvo una vez a punto de deslizarse
hacia la aprobación sin revisión fresca, porque la compuerta de revisión no
tenía regla para volver a correr después de las ediciones. El humano lo atrapó
e hizo la pregunta obvia, y la respuesta se volvió mecanismo en menos de una
hora. Un borrador editado materialmente es un borrador nuevo, y ningún
borrador llega al humano sin un panel de lectura en frío con contexto aislado.
Ese panel ha atrapado desde entonces un
error de conteo, una inconsistencia de métrica y un punto débil de privacidad
antes de que cualquiera de ellos llegara al público. El documento que usted
está leyendo fue auditado por maquinaria a la que no le importa que esté
describiéndose a sí misma, y la revisión que usted está leyendo volvió a pasar
por esa misma compuerta.

## El compromiso que nunca existió

Un incidente en vivo con un cliente. Un miembro del equipo resumió el estado
de la situación para una actualización a un interesado, incluida la línea "the team
would continue reviewing activity across other systems" (que el equipo
continuaría revisando la actividad en otros sistemas), un plan.
La IA redactó el mensaje saliente y el plan quedó como "we are also
checking your other systems" (también estamos revisando sus otros
sistemas), trabajo en curso. Ningún chat, ningún
ticket y ningún mensaje decía que ese trabajo existiera. El humano lo atrapó
con una sola pregunta, ¿de verdad estamos haciendo eso?, y la corrección tomó
un minuto. El mecanismo tomó solo unos minutos más. Toda afirmación que
compromete al equipo a una acción ahora tiene que rastrearse hasta un
compromiso registrado, un chat, un ticket, un mensaje o la indicación directa
del humano. Sin fuente, la línea sale del borrador y pasa a una lista de
sugerencias etiquetada. Las acciones planeadas se quedan en tiempo de plan. La
lección es que una IA que redacta en nombre de un equipo puede inventar
obligaciones tan fácilmente como hechos, con una edición tan pequeña como
pasar de "revisaremos" a "estamos revisando", y la regla aterrizó en la
doctrina en la misma sesión, en medio del trabajo del que surgió.

## Dos IA discuten hasta ponerse de acuerdo

Una construcción de ingeniería nocturna necesitaba enviarse con confianza, y
la directiva fue una sola línea: asegurar que los dos modelos estén de
acuerdo. El modelo autor y un auditor de un segundo proveedor corrieron cinco
rondas adversariales, cada ronda verificando de nuevo las correcciones de la
ronda anterior con citas exactas de los archivos vigentes, con el conteo de
hallazgos autorizado a bajar solo cuando una corrección era verificablemente
real. Ronda tras ronda el conteo cayó, y la disciplina atrapó
dos fallas que un solo modelo habría pasado por alto. Dos correcciones habían
sido "aplicadas" por scripts cuya coincidencia de texto se había desviado, así
que nada cambió en realidad mientras los borradores afirmaban que sí; la
reverificación del auditor expuso ambas, y desde entonces cada parche afirma
su coincidencia o falla ruidosamente.
El auditor también corrigió la propia contabilidad del implementador,
veintitrés hallazgos donde el implementador contaba veintiuno. El
intercambio terminó en un veredicto acordado por escrito, y las afirmaciones
falsas de parches se quedaron en el registro de procedencia en lugar de
reescribirse hasta desaparecer. La confianza salió de la discusión, que es
para lo que la discusión existe.

## El modelo operativo sale de casa

Un equipo en el entorno de demostración levantó un asistente interno de
documentación, un espacio de trabajo de IA compartido sobre una base de
conocimiento, y esperaba que aprendiera con el uso. Las herramientas de ese
tipo no aprenden con el uso. Lo que tienen son palancas, y las palancas son
exactamente aquellas sobre las que corre este sistema.
En una sola sesión de trabajo, el modelo operativo personal se adaptó a menor escala
para convertirse en un kit de
inicio para la herramienta del equipo: instrucciones de proyecto jugando el
papel que aquí juega la doctrina, responder solo desde la documentación, citar
la fuente y su fecha, negarse a adivinar, nunca emitir credenciales, declarar
la cobertura con honestidad; un archivo de contexto jugando el papel de la
capa de referencia, la jerga abreviada, el conjunto de herramientas, dónde
vive la documentación; y una bitácora de brechas con una cosecha periódica
jugando el papel del registro de atrapadas (una atrapada, un error detectado
por el humano), cada fallo convirtiéndose en un documento corregido o un
ajuste de instrucciones con un registro de cambios fechado. Una nota de
reconstrucción de una página sacó la reconstrucción de la cabeza de una sola
persona. El punto es que el context
engineering (la ingeniería de contexto) se transfiere. La misma disciplina que
corre el sistema de una persona, curar lo que el modelo sabe, construir el
ciclo que captura lo que se le escapa, versionar las instrucciones como
doctrina, levanta un asistente para todo un equipo en una tarde, y protege
contra la misma falla contra la que protege en casa, confiar en el
aprendizaje ambiental en lugar de mecanismos construidos.

## El hilo que recorre todo

Cada uno de estos dominios, incluido el espacio de trabajo donde se prepara
este documento, se ajusta ahora al mismo esqueleto de nueve partes descrito en
la tesis, uno nacido de él y el resto evaluados contra él con las brechas
encontradas cerradas y las desviaciones nombradas, y cada uno de
estos ejemplos es el mismo patrón con ropa distinta.
Escribir la regla donde se carga. Verificar contra una fuente, no contra una
memoria. Dejar que la maquinaria cace la deriva. Y cuando el humano de todos
modos atrapa algo, convertir la atrapada en un mecanismo.
