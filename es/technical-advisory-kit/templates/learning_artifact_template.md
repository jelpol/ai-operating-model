# Plantilla de artefacto de aprendizaje

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

Cópiela en cada archivo nuevo de `my-data/learnings/` o `my-data/validations/`. El front-matter (el bloque de metadatos inicial) mantiene consultable una carpeta plana y hace legible el ciclo de vida de cada artefacto.

```yaml
---
title:        # legible para humanos
type:         # explanation (explicación) | reference (referencia)  (solo aprendizajes; explanation es durable, reference vence)
domain:       # p. ej., identity, detection-eng, ai-ml, networking
tags:         # [etiquetas, libres, para, recuperación]
date:         # YYYY-MM-DD de creación
updated:      # YYYY-MM-DD de la última edición en su lugar
confidence:   # established-fact | consensus-best-practice | judgment-call  (hecho establecido, mejor práctica de consenso, juicio profesional)
sources:      # [urls / documentos contra los que se verificó]
expires:      # YYYY-MM-DD  (solo tipos reference y validaciones de hechos de proveedor; omítalo para explicación durable)
---
```

Cuerpo de un artefacto del Módulo 01 (anclaje de la investigación), cinco secciones:

1. Mapeo a marcos
2. Análisis de brechas del marco
3. Mi lectura de brechas (owned (dominado) / adjacent-new (nuevo adyacente) / new (nuevo), con orden de ejercicios y comprobaciones)
4. Lectura de aprovechamiento
5. Pasada de enlace ([[wikilinks]] a artefactos relacionados, en ambas direcciones)

Cuerpo de un artefacto del Módulo 02 (validación):

1. Veredicto (Sólido / Sólido con salvedades / Defectuoso, en inglés Sound / Sound with caveats / Flawed)
2. Tabla de hallazgos de las seis dimensiones
3. Salvedades o correcciones requeridas
4. Nota de vencimiento si el veredicto descansa en hechos de proveedor o de versión

Versionado: edite los artefactos en su lugar y deje que el historial de git (o una línea de cambio fechada dentro del archivo) registre qué se creía y cuándo. Sin copias hermanas fechadas. Un [[wikilink]] a un archivo que todavía no existe es un buen marcador de pendiente.
