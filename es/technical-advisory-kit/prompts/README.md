# Kit de asesoría técnica: manual de operación

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)

## Qué es esto

Un método para usar una IA como compañera de estudio técnico y revisora de diseños sin absorber sus alucinaciones ni sus halagos. Tres módulos para pegar más un archivo de principios, construidos alrededor de dos artefactos que le pertenecen: un registro de conocimientos (qué sabe, a qué profundidad y qué brechas siguen abiertas) y una carpeta creciente de aprendizajes anclados y veredictos conservados.

## Los módulos

| Módulo | Propósito |
|---|---|
| `01_research_anchoring.md` | Protocolo de estudio: mapee el material a los marcos rectores, declare los puntos ciegos de esos marcos, nombre SUS brechas con un orden de ejercicios, evalúe cómo puede aprovecharse, enlace con aprendizajes previos |
| `02_validate_a_design.md` | Motor de veredictos: seis dimensiones, tres veredictos (Sólido / Sólido con salvedades / Defectuoso, en inglés Sound / Sound with caveats / Flawed) |
| `03_verification_gate.md` | Compuerta de respuestas para toda la sesión: reglas antialucinación, rigor de Nivel A/B, jerarquía de confianza de fuentes |
| `principles.md` | Las reglas permanentes, escalonadas por precedencia |

## Sus archivos de datos (todos en `my-data/`, todos privados)

| Archivo | Qué contiene |
|---|---|
| `knowledge_registry.md` | Dominios de experto, competencia funcional, brechas abiertas nombradas, dominios en crecimiento, bitácora de aprendizaje. Cópielo desde `templates/knowledge_registry_template.md`. |
| `learnings/` | Artefactos de estudio anclados del Módulo 01, un archivo por cada uno, con front-matter (el bloque de metadatos inicial) según la plantilla |
| `validations/` | Veredictos conservados del Módulo 02 que valga la pena citar después |

## Criterios de promoción: qué se conserva

La mayor parte del contenido de una sesión no merece archivo alguno. Promueva solo cuando supere el listón:

1. A `learnings/` cuando la enseñanza es durable y reutilizable: la querría de nuevo en una sesión futura y es más que un dato de una línea. Etiquete el tipo: explanation (explicación, razones duraderas) o reference (referencia, hechos que vencen). Nunca ambos en un mismo archivo.
2. A `validations/` cuando un veredicto vale la pena citarse después: una decisión de diseño, una evaluación de producto, un "elegimos X por Y" al que su yo del futuro hará referencia.
3. Todo lo demás se queda en las notas de sesión o en ninguna parte. Una carpeta de aprendizajes inflada que nadie lee es peor que una delgada. La promoción es un impuesto; páguelo solo donde rinde.

## Front-matter del artefacto

Cada artefacto durable abre con el bloque de `templates/learning_artifact_template.md` (título, tipo, dominio, etiquetas, fechas, confianza, fuentes, vencimiento). Las carpetas planas sin front-matter se degradan hasta volverse una pila imposible de buscar.

## El ritmo

1. **Por sesión:** pegue primero `03_verification_gate.md`; gobierna todo el chat. Cierre actualizando el registro si su nivel cambió.
2. **Por elemento de estudio:** ejecute el Módulo 01. La lista de brechas y el orden de ejercicios son el entregable; el mapeo por sí solo es teatro de comprensión.
3. **Por decisión de diseño:** ejecute el Módulo 02. Conserve el veredicto solo si su yo del futuro lo va a citar.
4. **Mensualmente:** vuelva a revisar todo aquello cuya fecha de vencimiento haya pasado, concilie contradicciones y confirme que el registro sigue correspondiendo a la realidad.
