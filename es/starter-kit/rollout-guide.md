# Guía de implementación: levante los cimientos y su primer espacio de trabajo (workspace) en una sola sesión guiada

*Edición en español (México), traducida de la versión inglesa: el commit 40494f3 y la revisión inglesa del 2026-09-06, que se publica en el mismo commit que esta traducción. La versión en inglés es la canónica.*

Lo que necesita. Claude Code instalado y con sesión iniciada, git
instalado y un repositorio nuevo PRIVADO (un repositorio privado de
GitHub es lo más sencillo; un repositorio solo local funciona,
simplemente omita los push, el envío de cambios al repositorio remoto).
Nada más. Los prompts de abajo hacen la
construcción; usted toma las decisiones que ellos le piden. Si ya tiene
un repositorio con trabajo dentro, lea "Si ya tiene un repositorio", al
final de esta guía, antes del Paso 1.

Una regla antes de comenzar, porque es la que hace funcionar todo lo
demás: usted es quien ratifica. La IA propondrá; nada se convierte en
regla de su sistema hasta que usted diga que sí. Si conserva un solo
hábito de esta guía, que sea ese.

## Lo que esta sesión construye, y lo que no

Construido al terminar el Paso 5: un archivo raíz de instrucciones que se
carga en cada sesión, un archivo de mantenimiento con un registro de
atrapadas vacío y una plantilla de tablero de calificación mensual, un
workspace construido a partir del esqueleto de nueve partes y el comando
de ingesta. Eso son los cimientos y un dominio de trabajo, y con ello
queda completo el ciclo de gobernanza del kit para ese dominio. No
proporciona los controles que el README de este kit declara fuera de
alcance (modelado de amenazas, manejo de secretos, control de acceso y
los demás); esos siguen viniendo de su entorno.

Lo que no se construye aquí, cada punto con el detonante que hace que
valga la pena construirlo:

- Un segundo workspace, cuando llegue un segundo dominio de trabajo. El
  procedimiento está al final de esta guía; es el Prompt Dos otra vez.
- Una capa por encima de los workspaces (un tablero compartido, registros
  en los que escribe más de un dominio), cuando los hilos empiecen a
  cruzar dominios. La tesis la describe en su sección de arquitectura.
- Una segunda máquina. La memoria propia de Claude Code se guarda por
  máquina y no viaja en un clon; solo viaja lo que usted confirma con
  commit (la confirmación de cambios en git). Decida qué se queda local
  (memoria, credenciales) antes de clonar a una segunda computadora.
- Un segundo modelo, ejecutando el protocolo de revisión adversarial, el
  día que quiera una revisión que no comparta los puntos ciegos del autor.

Verificación del entorno de ejecución (harness). Los tres
comportamientos de los que depende esta guía se cotejaron contra la
documentación de Claude Code (las páginas sobre archivos de memoria y
sobre skills en code.claude.com/docs) el 2026-09-06, con Claude Code
2.1.224 instalado en ese momento; se leyeron de la documentación, no se
ejercitaron en una corrida registrada. Son: un CLAUDE.md en la raíz del
repositorio se carga al iniciar la sesión; un CLAUDE.md en una subcarpeta
se carga cuando la IA lee archivos ahí; y un comando que usted invoca por
su nombre se crea ya sea con un archivo en .claude/commands/<nombre>.md o
con una carpeta en .claude/skills/<nombre>/ que contenga un SKILL.md.
Vuelva a verificar esos tres cuando Claude Code cambie la forma en que
carga archivos de instrucciones, importaciones o skills, y actualice este
párrafo.

## Paso 1. Cree el repositorio base

Cree un repositorio privado y abra Claude Code dentro de él. Copie los
tres archivos de plantilla de este kit (`skeleton-template.md`,
`workspace-loader-template.md`, `intake-command-template.md`) a una
carpeta `templates/` en su repositorio. La cuarta plantilla,
`adversarial-review-protocol.md`, se incorpora después, el día que
agregue un segundo modelo; la sesión guiada de abajo solo necesita las
tres.

## Paso 2. Pegue el Prompt Uno, los cimientos

```
Lea los tres archivos en templates/. Usted me está ayudando a levantar un
sistema operativo de IA gobernado en este repositorio, modelado sobre el
marco que describen esas plantillas. Primero entrevísteme, una pregunta a
la vez: qué dominios de trabajo quiero ejecutar aquí (comenzando con uno
o dos), quién soy y cuáles son mis innegociables de honestidad. Después
cree: (1) un CLAUDE.md raíz que se cargue en cada sesión y que lleve solo
las reglas siempre verdaderas: que git es la fuente de la verdad, que
haga commit en cada sesión y push siempre que haya un remoto configurado
salvo que yo le haya dicho que el push requiere mi autorización cada vez,
que valide el enfoque conmigo antes de construir cualquier cosa, que
presente cada decisión abierta en un bloque numerado "Pendientes de
usted" al final de sus respuestas, que nunca afirme de memoria un dato de
proveedor, versión, precio o dependiente del tiempo sin verificación en
vivo, y que cuando yo corrija un error proponga una fila para el registro
de atrapadas y la regla permanente que previene la clase; (2) un
MAINTENANCE.md con un registro de atrapadas vacío (cada vez que yo lo
atrape en un error, se agrega aquí una fila emparejada con la regla
permanente que previene la clase) y una plantilla de tablero de
calificación mensual de cinco números. Muéstreme ambos archivos antes de
escribirlos. Nada es definitivo hasta que yo apruebe el texto exacto.
```

## Paso 3. Pegue el Prompt Dos, su primer espacio de trabajo (workspace)

```
Ahora levante mi primer workspace usando templates/skeleton-template.md
como marco. Entrevísteme una pregunta a la vez para llenar las nueve
partes para este dominio: los lentes que se aplicarán al construir, las
personas lectoras a las que va dirigido el trabajo, la rúbrica de
calificación, los controles de error, el ciclo de aprendizaje y adónde se
enrutan las lecciones, el límite honesto declarado, la compuerta de
verificación con mis detonantes de alto riesgo, si este dominio maneja
suficientes hilos paralelos como para necesitar un tablero de trabajo
permanente, y qué clases de documento se repetirán y necesitarán un
estándar por clase de documento. Cualquier parte que genuinamente no
aplique recibe una desviación nombrada con una razón, nunca se omite en
silencio. Después cree la carpeta del workspace con un cargador delgado
construido a partir de templates/workspace-loader-template.md, un índice,
el archivo de doctrina y una carpeta State con una entrada de génesis.
Muéstreme todo antes de escribir. Haga commit cuando yo apruebe, y push
si hay un remoto configurado.
```

## Paso 4. Pegue el Prompt Tres, el protocolo de ingesta

```
Instale el protocolo de ingesta de artefactos de
templates/intake-command-template.md como un comando personalizado en
este repositorio, adaptado a los nombres de mis workspaces. De ahora en
adelante, cuando yo suelte cualquier archivo y le pida que le dé sentido,
ejecute ese protocolo: léalo por completo, interrogue el encuadre
conmigo, archive la instancia con su propietario y deje tras de sí una
plantilla reutilizable. Confirme que el comando quedó instalado y
muéstreme cómo lo activo.
```

En el Claude Code actual, los comandos personalizados y los skills son un
mismo mecanismo con dos formatos admitidos: un solo archivo en
`.claude/commands/<nombre>.md`, o una carpeta en
`.claude/skills/<nombre>/` que contenga un `SKILL.md`. Cualquiera de los
dos crea un comando que usted invoca por su nombre. La IA debe instalarlo
en el formato que documente su versión.

## Paso 5. Compruebe que funciona

Suelte un archivo en una sesión y diga "ejecuta la ingesta de esto". Use
un archivo que sea seguro compartir con su proveedor de IA: nada
confidencial, regulado ni con credenciales, y revise sus propias reglas
de manejo de datos antes de usar material real. Atrape a la IA en un
error, cualquier error, y observe si ofrece
una regla permanente para el registro. Pregúntele "qué hay en la cola de
decisiones" al final de una sesión. Si las tres cosas se comportan como
deben, el ciclo está vivo y el sistema crecerá cada vez que usted lo
corrija.

Cómo debería verse el sistema después de un mes: su archivo raíz sigue siendo
corto, su registro tiene filas, su tablero de calificación tiene sus
primeros números honestos y usted le ha dicho que no al menos a una de
las propuestas de la IA. El no es la manera de saber que la gobernanza es
real.

## Cuando llegue el segundo dominio

Pegue de nuevo el Prompt Dos cambiando "mi primer workspace" por "mi
siguiente workspace" y nombrando el nuevo dominio. Mantenga la forma
idéntica a la del primero: un cargador delgado, un índice, el archivo de
doctrina, una carpeta State. La uniformidad es lo que mantiene navegables
varios workspaces; la doctrina dentro de cada uno es lo que los mantiene
distintos. El archivo raíz sigue siendo corto. Si está creciendo, algo
que pertenece a un workspace se ha filtrado hacia arriba.

## Si ya tiene un repositorio

Los prompts de arriba suponen un repositorio vacío. En uno que ya
contiene proyectos en funcionamiento, ejecute la sesión como una
adaptación, no como una construcción. Parta de un árbol de trabajo limpio
en una rama (branch) desechable. Dos reglas rigen desde aquí, pegue o no
el párrafo de abajo: nada se crea, se copia ni se cambia en este
repositorio hasta que usted haya aprobado esa ruta por su nombre, y no se
hace push hasta que usted lo indique. Antes de copiar cualquier cosa,
revise si ya existen `templates/`, `CLAUDE.md` o `MAINTENANCE.md`; si
alguno existe, decida desde ahora si se fusiona o si el material nuevo va
bajo otro nombre, y no lo sobrescriba. Después, con su aprobación, copie
los mismos tres archivos de plantilla del Paso 1 a `templates/` (o a la
carpeta con el nombre que haya elegido). Pegue este párrafo antes del
Prompt Uno, y otra vez antes del Prompt Dos:

```
Este repositorio ya contiene proyectos en funcionamiento. Antes de crear
cualquier cosa, haga un inventario del árbol, liste cada archivo o
carpeta que crearía y que ya existe, y proponga una fusión (merge) para
cada uno. No cambie nada hasta que yo apruebe cada ruta por su nombre. No
haga push hasta que yo lo indique, y en el archivo raíz de instrucciones
haga que el push requiera mi autorización explícita cada vez, no "siempre
que haya un remoto configurado"; yo mismo lo relajaré después si así lo
decido.
```

Exija que la primera pasada produzca una propuesta y ningún cambio, y
compruébelo usted mismo con `git status` y con el diff (la comparación
línea por línea) antes de aprobar nada. Apruebe por su nombre cada cambio
a un archivo existente y luego deje correr los prompts. Los proyectos
existentes se mapean sobre el marco de nueve partes, no se reconstruyen.
Cuando termine la sesión, ejecute las comprobaciones que sus proyectos ya
tenían; deben pasar exactamente como antes.
