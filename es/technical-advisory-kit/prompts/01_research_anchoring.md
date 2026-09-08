# Módulo 01: Anclaje de la investigación (01_research_anchoring)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Protocolo de estudio
**Úselo con:** cualquier artículo externo, informe técnico (writeup), herramienta, técnica o producto del que usted quiera aprender de verdad, no solo leer

## Qué hace este módulo

Convierte la lectura pasiva en comprensión anclada. Cada pieza de investigación se ata a los marcos rectores de su dominio, se declaran los puntos ciegos de esos mismos marcos y se nombran sus brechas personales con un orden de ejercicios. La idea fundacional: mapear el material a un marco es teatro de comprensión; la lista de brechas es el entregable.

## Cuándo NO usarlo

Una consulta factual rápida sigue siendo una respuesta de una línea. Este protocolo se dispara con material que usted estudia para adquirir competencia, nunca con consultas sencillas.

---

## PROMPT PARA PEGAR EN SU CHAT DE IA

Usted está ejecutando el **protocolo Research Anchoring** (anclaje de la investigación) sobre el material que el usuario proporciona. Asegúrese de que el usuario haya pegado o adjuntado: (1) el material en sí (artículo, informe técnico, documentación de la herramienta) y (2) el registro de conocimientos del usuario, tomado de `my-data/knowledge_registry.md`.

Produzca las cinco salidas siguientes en el artefacto, no solo en la conversación. El usuario guarda el resultado en `my-data/learnings/`.

**Salida 1: Mapeo a marcos.**
Mapee el material a los marcos que gobiernan su dominio. Para comportamiento adversario: MITRE ATT&CK (base de conocimientos de tácticas y técnicas de adversarios) para las técnicas y el Diamond Model (Modelo Diamante) para eventos, hilos y estructura de campaña, con la fase de la kill chain (cadena de ataque) superpuesta como metacaracterística del Diamond Model. Otros dominios usan su propio conjunto rector: NIST 800-171 (controles para información no clasificada controlada) o los benchmarks de CIS (Center for Internet Security) para trabajo de controles, ATT&CK más el ciclo de vida de detección para ingeniería de detección, y así sucesivamente. Nombre el marco que eligió y por qué.

**Salida 2: Análisis de brechas del marco.**
Declare qué es lo que los marcos elegidos FAIL (no logran) capturar de este material. Esta es la mitad que se omite y la mitad que más importa. Un conjunto de controles derivado de un marco hereda los puntos ciegos de ese marco, así que un punto ciego no declarado se convierte en una exposición no declarada.

**Salida 3: La lectura de brechas del propio usuario (la salida principal).**
Contra el registro de conocimientos, nombre los conocimientos que este material exige que el usuario comprenda y clasifique esos conocimientos en tres categorías:
1. owned (dominado): ya dominado a nivel de pares.
2. Adjacent-new (nuevo adyacente): la base está, el detalle específico falta.
3. Genuinely new (genuinamente nuevo): el concepto mismo es nuevo.
Después dé el orden de ejercicios (el de mayor aprovechamiento primero) y la comprobación de cada ejercicio, es decir, cómo sabrá el usuario que ya lo tiene. Agregue las filas nuevas a la tabla de brechas nombradas del registro. Esta salida trata de la comprensión del usuario, nunca de calificar los controles de su empleador o de sus clientes. Ejecute una lectura de controles organizacionales solo si el usuario lo pide explícitamente, y manténgala subordinada a la lectura de aprendizaje.

**Salida 4: Lectura de aprovechamiento.**
Cómo se usa realmente la herramienta o técnica y cómo podría aprovecharse, de forma ofensiva y defensiva. El material de doble uso es corpus de estudio legítimo; la compuerta es la autorización y el etiquetado, nunca la aprensión.

**Salida 5: Pasada de enlace.**
Indique explícitamente con qué se conecta este material dentro de lo que el usuario ya estudió, por nombre de artefacto en `my-data/learnings/`, y qué cambia respecto de esa comprensión anterior. Los hechos aislados no se convierten en competencia; los conectados sí. Haga referencias cruzadas con [[wikilinks]] en ambas direcciones.

**Disciplina de identificadores (regla bloqueante).**
Los identificadores de marcos son hechos del proveedor sujetos a versión: los ID de técnica de ATT&CK, los ID de control de NIST y los números de benchmark de CIS se verifican contra la fuente en vivo antes de escribirse, nunca se citan de memoria. Un ID sin fuente verificada no entra en el artefacto. Si no puede verificar en este chat, marque el ID como "[UNVERIFIED: verifique antes de confiar en esto]" (UNVERIFIED, no verificado).

**Lo que no encaja se registra, no se omite.**
Cuando el material genuinamente no tiene marco rector, dígalo en una línea y diga qué ocupa su lugar. Una ruta de estudio para certificación, por ejemplo, es plan de estudios y no comportamiento adversario, así que lleva una referencia a un contrapeso de seguridad en lugar de un mapeo a marcos.

**Formato de salida.**
Un solo artefacto markdown con las cinco salidas como secciones, que abre con el bloque de front-matter de `templates/learning_artifact_template.md`, listo para guardarse en `my-data/learnings/`.
