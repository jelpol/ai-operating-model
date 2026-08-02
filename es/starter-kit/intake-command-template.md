# Protocolo de ingesta de artefactos (plantilla)

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Guárdelo como un comando personalizado (para Claude Code: `.claude/commands/intake.md`) o
ejecútelo a mano como una lista de verificación. El detonante es cualquier
artefacto entregado, una hoja de cálculo, un documento, una configuración,
cualquier cosa que alguien haya construido y que usted quiera entender,
mejorar o repetir. El resultado siempre tiene dos capas. La instancia se
archiva con su dueño, y la plantilla reutilizable se archiva donde el
siguiente proyecto la encuentre.

## Paso 1. Lea el artefacto por completo

Estructura, cada hoja o sección, fórmulas, convenciones y el método
incorporado en él. Verifique cualquier afirmación técnica que haga el
artefacto cuando sea de alto riesgo. Haga visibles los errores y las
inconsistencias ante el humano, y nunca corrija en silencio el trabajo de
otra persona.

## Paso 2. Interrogatorio de encuadre (validar antes de construir)

Pregunte al humano y obtenga su acuerdo antes de escribir cualquier cosa
reutilizable. Omita una pregunta solo declarando en voz alta la respuesta
que se asume.

1. Propósito y audiencia. ¿Quién consume esto, y a través de qué persona?
2. Cómo se ve lo bueno. ¿Qué hizo valioso este artefacto, y qué tiene de
   malo?
3. Ambición de reutilización. ¿De un solo uso, para este cliente o su
   familia, o para todas partes?
4. Dominio propietario. ¿Dónde vive la instancia, a dónde va la plantilla,
   las reglas de quién se le aplican?
5. Necesidades de verificación. ¿Qué debe comprobarse antes de que alguien
   dependa de él?
6. Sensibilidades. Datos privados, exposición de precios, cualquier cosa
   que no deba salir del edificio.

## Paso 3. Archive la instancia

Con su dueño, archive el artefacto en su formato nativo, con una
instantánea en texto plano a su lado para que sea comparable con un diff
(la comparación línea por línea) y revisable, y con notas de instancia que
registren estructura, hallazgos y estado de verificación.

## Paso 4. Construya la capa reutilizable

En la ubicación de plantillas del dominio propietario, deje una
especificación de plantilla que cubra estructura, fórmulas, método,
decisiones de diseño y qué adaptar en cada uso, más una rúbrica de
calificación contra la cual se evaluarán las instancias futuras.

## Paso 5. Cierre

Registre la lección en el ciclo de aprendizaje, incluida la bandeja de
entrada entre dominios si la lección es de nivel de sistema. Haga commit.
El siguiente "hazme uno como este" debería ser una petición de una sola
línea.
