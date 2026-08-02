# Guía de implementación: levante el marco en una sola sesión guiada

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Lo que necesita. Claude Code instalado y con sesión iniciada, git
instalado y un repositorio nuevo PRIVADO (un repositorio privado de
GitHub es lo más sencillo; un repositorio solo local funciona,
simplemente omita los push). Nada más. Los prompts de abajo hacen la
construcción; usted toma las decisiones que ellos le piden.

Una regla antes de comenzar, porque es la que hace funcionar todo lo
demás: usted es quien ratifica. La IA propondrá; nada se convierte en
regla de su sistema hasta que usted diga que sí. Si conserva un solo
hábito de esta guía, que sea ese.

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
haga commit en cada sesión y push siempre que haya un remoto configurado,
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

## Paso 5. Compruebe que funciona

Suelte cualquier archivo real en una sesión y diga "ejecuta la ingesta de
esto". Atrape a la IA en un error, cualquier error, y observe si ofrece
una regla permanente para el registro. Pregúntele "qué hay en la cola de
decisiones" al final de una sesión. Si las tres cosas se comportan como
deben, el ciclo está vivo y el sistema crecerá cada vez que usted lo
corrija.

Cómo debería verse el sistema después de un mes: su archivo raíz sigue siendo
corto, su registro tiene filas, su tablero de calificación tiene sus
primeros números honestos y usted le ha dicho que no al menos a una de
las propuestas de la IA. El no es la manera de saber que la gobernanza es
real.
