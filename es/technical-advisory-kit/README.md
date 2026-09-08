# Kit de asesoría técnica

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

Un método (en inglés, Technical Advisory Kit) para usar una IA como compañera de estudio técnico y revisora de diseños sin absorber sus alucinaciones ni sus halagos. Construido y probado en condiciones reales dentro del modelo operativo que este repositorio documenta, y después saneado para publicarse como kit de inicio.

**¿Es nuevo aquí? Lea [START_HERE.md](START_HERE.md). Es todo el proceso de incorporación.**

## Qué es

1. Tres módulos para pegar en [prompts/](prompts/): un protocolo de anclaje de la investigación (mapee el material a sus marcos rectores, declare los puntos ciegos de esos marcos, nombre SUS brechas con un orden de ejercicios), un motor de validación de diseños (seis dimensiones, tres veredictos) y una compuerta de verificación para toda la sesión (reglas antialucinación con una jerarquía de confianza de fuentes y un rigor escalonado según lo que está en juego). [prompts/README.md](prompts/README.md) es el manual de operación.
2. Una [plantilla de registro de conocimientos](templates/knowledge_registry_template.md): el mapa honesto de lo que usted sabe y a qué profundidad, que la IA lee para calibrar entre enseñar y revisar entre pares.
3. Una [plantilla de artefacto de aprendizaje](templates/learning_artifact_template.md) con front-matter (el bloque de metadatos inicial) que mantiene su base de conocimientos consultable y con seguimiento de fechas de vencimiento.

## La idea central

Mapear el material de estudio a un marco es teatro de comprensión. Los entregables que generan valor acumulativo son los puntos ciegos declarados del marco, sus brechas nombradas con ejercicios para cerrarlas y los enlaces hacia lo que usted ya aprendió. Lo mismo aplica a la revisión de diseños: una IA que está de acuerdo con usted no vale nada; el veredicto de seis dimensiones obliga a evaluar el diseño desde la perspectiva del pentester, del auditor y del ingeniero de guardia de las 3 a. m.

## Privacidad

Su registro y sus aprendizajes viven en `my-data/`, que se entrega vacía y excluida de git mediante .gitignore. Los prompts son públicos; el mapa de sus propias fortalezas, debilidades y entorno no lo es.

## Relación con el repositorio en su conjunto

Este kit es el dominio de asesoría técnica del [modelo operativo](../thesis.md), exportado para su reutilización, junto con el [kit de inicio](../starter-kit/) (el esqueleto del marco) y el [kit de adaptación de currículum](../resume-tailoring-kit/) (el dominio de búsqueda de empleo). La prosa es CC BY 4.0; las plantillas y los módulos de prompt son MIT; vea [LICENSE](LICENSE).
