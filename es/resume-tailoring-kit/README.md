# Kit de adaptación de currículum

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

Un pipeline de prompts completo y funcional (en inglés, Resume Tailoring Kit) para adaptar su currículum a puestos específicos con un asistente de IA, sin permitir que la IA invente su carrera. Construido y probado en condiciones reales durante una búsqueda de empleo de nivel sénior dentro del modelo operativo que documenta este repositorio, y después despersonalizado para convertirlo en un kit de inicio público.

**¿Es nuevo aquí? Lea [START_HERE.md](START_HERE.md). Ahí está toda la orientación inicial.**

## Qué es

1. Quince módulos de prompts numerados en [prompts/](prompts/) que usted pega en cualquier chat de IA capaz: ingesta de la descripción del puesto (JD), calificación, interrogatorio de brechas, construcción del contenido en dos versiones, PRINT (impresa, para humanos) y ATS (sistema de seguimiento de candidatos, para el software de análisis), verificación de hechos, carta de presentación, control de calidad con revisiones simuladas de reclutador, ATS y gerente de contratación, preparación para la entrevista, y más. [prompts/README.md](prompts/README.md) es el manual de operación.
2. Una [plantilla de registro de hechos](templates/fact_registry_template.json): la columna vertebral antialucinación. Cada afirmación del currículum debe rastrearse hasta un hecho que usted confirmó con sus propias palabras.
3. Una [hoja de trabajo de tesis de carrera](templates/career_thesis_template.md) para que el pipeline pueda decirle qué puestos merecen realmente su esfuerzo.
4. [WHY_THIS_WORKS.md](WHY_THIS_WORKS.md): una página sobre el razonamiento, los tres filtros entre usted y una entrevista, y lo que este kit deliberadamente no hará.

## Qué no es

No fabrica experiencia, no infla títulos ni promete entrevistas. La disciplina corre en sentido contrario: alcance honesto, afirmaciones respaldadas por evidencia y un registro que usted puede defender línea por línea en la sala de entrevista.

## Privacidad

Los prompts son públicos; sus datos no. Todo lo personal vive en `my-data/`, que se entrega vacía y debe permanecer privada. Si bifurca (fork) este kit, `my-data/` ya está excluida por gitignore; manténgala así.

## Relación con el repositorio general

Este kit es el dominio de búsqueda de empleo del [modelo operativo](../thesis.md) exportado para su reutilización, de la misma manera en que el [kit de inicio](../starter-kit/) exporta el esqueleto del marco. La prosa es CC BY 4.0, las plantillas y los módulos de prompts son MIT; vea [LICENSE](LICENSE).
