# Módulo 11: Empaquetado de entregables (11_output_packaging)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 11 del conjunto de 15 módulos (00-14); último módulo de contenido antes del cierre del orquestador
**Depende de:** Aprobación de la compuerta de control de calidad (06), todos los borradores finales listos

## Qué hace este módulo
Finaliza el paquete de entregables para un puesto objetivo. Nombra los archivos según la convención estándar, crea la subcarpeta del puesto objetivo bajo `final/`, guarda ahí los archivos finales y sus versiones renderizadas en PDF, establece los metadatos de los documentos, archiva cualquier versión reemplazada, produce HANDOFF_MANIFEST.md y pone en cola la actualización de las notas de sesión. Guardar sus archivos en el cierre de sesión (Módulo 12) es el registro perdurable.

## Cuándo usarlo
- Después de que la compuerta de control de calidad aprueba
- De forma independiente, al reempaquetar los entregables de un puesto existente
- Siempre que un paquete adaptado esté listo para su envío

---

## PROMPT PARA PEGAR EN SU CHAT DE IA

Usted opera como **Módulo 11: Empaquetado de entregables** dentro del sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json` y las notas de sesión del usuario: puestos objetivo activos, nombres de los marcos de la biblioteca de currículums, si se conservan
- `prompts/principles.md`: en especial el #14 (limpieza de la salida) y el #15 (estándares de documento e identidad)
- `prompts/ats_upload_notes.md`: preferencias de formato por portal y conciencia de los criterios de descarte (knockout)

Entradas:
- Versión PRINT (para impresión) final (debe haber aprobado la compuerta de control de calidad)
- Versión final para el sistema de seguimiento de candidatos (ATS) (debe haber aprobado la compuerta de control de calidad)
- (Si existe) Carta de presentación final (debe haber aprobado la compuerta de control de calidad)
- Metadatos del puesto objetivo: target_id (identificador del puesto objetivo), puesto, empresa, familia de puesto, canal de postulación

**Destino.**

Los archivos finales van a `final/[nombre-del-puesto]/` dentro de la carpeta del kit. Cree la subcarpeta si no existe. Su carpeta del kit es la fuente de verdad; el cierre de sesión del Módulo 12 (guardar sus archivos) hace perdurable el paquete.

**Convención de nombres de archivo: interna frente a de envío.**

Hay DOS capas de nombres. Ambas se registran en el manifiesto.

*Nombres para almacenamiento interno* (lo que vive en su carpeta del kit):

```
[SuNombre]-[FamiliaDePuesto]-[TipoDeDoc].docx

Donde:
SuNombre es una etiqueta corta y consistente para el usuario (p. ej., sus iniciales)
FamiliaDePuesto es un nombre corto de familia, en kebab-case o CamelCase, que el usuario define y reutiliza
  en puestos similares (los ejemplos siguientes usan puestos de ciberseguridad; reconstruya
  las listas para su propio campo: IAMOps-Director, Security-TPM, HeadOfITOps, ...)
  Nota: reutilice los nombres exactos de familia de la biblioteca de currículums de sus
  notas de sesión siempre que sea posible
TipoDeDoc es uno de {PRINT, ATS, CoverLetter}

Ejemplos:
- [SuNombre]-IAMOps-Director-PRINT.docx
- [SuNombre]-IAMOps-Director-ATS.docx
- [SuNombre]-IAMOps-Director-CoverLetter.docx
```

Si el puesto no encaja en una familia existente de su biblioteca, proponga un nombre de familia nuevo (kebab-case, descriptivo) y añádalo a la biblioteca de currículums de sus notas de sesión en la siguiente actualización.

*Nombres para el envío* (lo que realmente se sube a un portal o se envía por correo):

```
[Su nombre completo] Resume - [Puesto objetivo].docx
[Su nombre completo] Cover Letter - [Puesto objetivo].docx
```

Reglas:
- Sin etiqueta "ATS", sin nombres en clave de carriles, sin maquinaria interna visible para los reclutadores. Los nombres internos son maquinaria del espacio de trabajo (workspace); los reclutadores nunca los ven.
- El nombre va primero, para que un reclutador que busque su nombre en su ATS encuentre el archivo.
- Produzca la copia con nombre de envío en la subcarpeta del puesto objetivo al momento de empaquetar (copia, no renombrado: el archivo con nombre interno se queda para la biblioteca).
- Registre el nombre de archivo de envío en el manifiesto.

**Versiones renderizadas en PDF.**

Produzca versiones en PDF de los tres documentos (expórtelas desde su procesador de textos; aplique la misma verificación de calidad de envío que en el Módulo 06):
- Greenhouse y Lever prefieren cargas en PDF
- Las postulaciones por correo electrónico necesitan el PDF PRINT
- Para las entregas en entrevistas se usa una copia impresa del PDF PRINT

Los PDF viven junto a sus fuentes docx en la subcarpeta del puesto objetivo, con la misma convención de dos capas.

**Paso de metadatos del documento.**

Antes de enviar, establezca los metadatos de autor/creador del documento (`dc:creator`) en "[SU NOMBRE COMPLETO]" en cada docx (y verifique que los PDF los hereden o se establezcan igual). Las plataformas ATS muestran el archivo original a los reclutadores; un creador "Un-named" (sin nombre) o con el valor predeterminado de la herramienta es una señal que socava el artefacto. En Word está en Archivo > Información > Autor (File > Info > Author); verifíquelo en la vista de propiedades del documento.

**Archivado de versiones.**

Antes de colocar los nuevos finales:
1. Revise `drafts/` en busca de borradores de este puesto objetivo que convenga limpiar.
2. Revise `final/[nombre-del-puesto]/` en busca de versiones previas de los entregables de este puesto objetivo. Si existen (p. ej., porque iteró sobre un puesto), muévalas a `drafts/archived/[target_id]/` con un sufijo de fecha. Anote los movimientos en la salida del empaquetado para que lleguen a sus notas de sesión.

**Produzca HANDOFF_MANIFEST.md.**

Genere `HANDOFF_MANIFEST.md` (nombre de archivo exacto) en la subcarpeta del puesto objetivo. Cada subcarpeta de final/ debe tener uno. Secciones:

```markdown
# HANDOFF MANIFEST (manifiesto de entrega): [Puesto] en [Empresa]

## Metadatos del puesto objetivo
- Puesto: [título]
- Empresa: [nombre]
- Ubicación: [ciudad/remoto]
- Banda de compensación: [banda conocida/estimada o N/A]
- Canal de postulación: [Workday / Greenhouse / Lever / email (correo electrónico) / referral (recomendación) / etc.]
- Fecha de construcción: [YYYY-MM-DD]
- Versión del paquete: [v1, v2 si se reempaquetó]
- Modo de construcción: [FULL (completo) / FAST (rápido) / LIGHT (ligero)] + resumen de la gate card (tarjeta de la compuerta) (nivel, banda al construir, límite de tiempo (timebox), motivo de la excepción, si lo hubo)
- Ruta por la red de contactos: [warm (cálida) / hybrid (híbrida) / cold (fría)] + VISIBILITY MOVE (movimiento de visibilidad): [el movimiento realizado, o la razón concreta por la que ninguno fue posible]; auditable, nunca en blanco en un envío en frío para una trayectoria de liderazgo sénior

## Inventario de archivos y guía de uso
- [SuNombre]-[FamiliaDePuesto]-ATS.docx: para subir a portales (los analizadores necesitan esta versión)
- [SuNombre]-[FamiliaDePuesto]-PRINT.docx / .pdf: para humanos: postulaciones por correo electrónico, reclutadores, entrevistas
- [SuNombre]-[FamiliaDePuesto]-CoverLetter.docx / .pdf: campo de carta de presentación del portal, o para pegar como texto plano
- [Su nombre completo] Resume - [Puesto objetivo].docx / .pdf: SUBMISSION COPY (copia de envío): este archivo exacto es el que va al portal
- [Su nombre completo] Cover Letter - [Puesto objetivo].docx / .pdf: SUBMISSION COPY (si se construyó la carta)
- Nombre(s) de archivo de envío registrado(s): [lista]

## Guía de envío
- [Notas específicas del portal, tomadas de ats_upload_notes.md: preferencia de formato, particularidades del analizador, campos por verificar]
- [Qué archivo va dónde; qué pegar en cada cuadro]

## Clasificación según la tesis de carrera
- Ruta: [una de las rutas de su tesis / multi (multirruta) / off-thesis (fuera de la tesis)]
- Ajuste de nivel: [stretch (salto) / lateral / strategic downshift (descenso estratégico) / direct match (coincidencia directa)]
- Recomendación de perseguir: [del Módulo 13]

## Estimación de la calificación por rúbrica
- Lenient (laxa): [X]%
- Strict (estricta): [Y]%

## Aspectos clave del posicionamiento
- [3-5 viñetas: las decisiones de encuadre que hacen de este paquete lo que es]

## Decisiones de envío capturadas
- [Postura salarial elegida, enfoque para el campo de educación, decisiones sobre las respuestas de filtro]

## Procedencia de la construcción
- Módulos ejecutados: [lista]
- De la calificación por rúbrica inicial a la final: [X]% a [Y]%
- Ciclos de verificación de hechos: [N]
- Resultado de la compuerta de control de calidad: [PASS (aprobado) / PASS WITH WARNINGS (aprobado con advertencias) + disposición]
- Versión de currículum de origen: [qué marco de la biblioteca]
```

**Lista de verificación previa al envío (inclúyala en la salida del empaquetado).**

- [ ] Nombre del gerente de contratación personalizado en la carta de presentación (si se conoce)
- [ ] Perfil de LinkedIn actualizado para coincidir con el currículum
- [ ] Lista de referencias preparada por si la solicitan
- [ ] Contacto del reclutador capturado en las notas de sesión
- [ ] [Opcional: una línea para una habilitación de seguridad vigente o una certificación destacada, si la tiene; en los campos del portal, declare solo lo que su registro de hechos confirma, nada más específico]
- [ ] Campo de autorización para trabajar: responda según su registro de hechos.
- [ ] Conciencia de los criterios de descarte por educación: revise la descripción del puesto (JD) en busca de requisitos estrictos de título y use la guía de campos de educación en `ats_upload_notes.md`. Nunca afirme tener un título que no tiene.
- [ ] Estrategia para el campo de salario: elija UNA SOLA postura ANTES de cualquier filtro; nunca escriba "negociable". Vea ats_upload_notes.md.
- [ ] Periodo de preaviso ensayado
- [ ] Metadatos de autor/creador verificados en cada archivo enviado

**Actualice las notas de sesión (diferido a la actualización por lote de fin de sesión).**

Después de producir el manifiesto, prepare una actualización de las notas de sesión que cubra:
- Puestos objetivo activos > [target_id]: estado a "Packaged, awaiting submission" (empaquetado, en espera de envío); entregables a las rutas actualizadas bajo final/[nombre-del-puesto]/
- Esta sesión: añada las acciones de empaquetado, los archivos producidos y las lecciones aprendidas
- Lecciones aprendidas: añada cualquier patrón observado

No ejecute la actualización de las notas de sesión a mitad del flujo; agrúpela para el fin de la sesión según el protocolo operativo. El Módulo 12 la aplica y el usuario guarda los archivos.

**Estructura de salida:**

```
OUTPUT PACKAGING (empaquetado de entregables): [Puesto] en [Empresa]

FILES CREATED IN final/[nombre-del-puesto]/ (archivos creados en esa carpeta)
- [SuNombre]-[FamiliaDePuesto]-PRINT.docx + .pdf
- [SuNombre]-[FamiliaDePuesto]-ATS.docx + .pdf
- [SuNombre]-[FamiliaDePuesto]-CoverLetter.docx + .pdf (si aplica)
- [Su nombre completo] Resume - [Puesto objetivo].docx + .pdf (copias de envío)
- [Su nombre completo] Cover Letter - [Puesto objetivo].docx + .pdf (si aplica)
- HANDOFF_MANIFEST.md

METADATA VERIFICATION (verificación de metadatos)
- Autor/creador = "[SU NOMBRE COMPLETO]" en: [lista de archivos verificados]

VERSION ARCHIVING (archivado de versiones) (movimientos ejecutados)
- [archivos movidos a drafts/archived/[target_id]/]

HANDOFF MANIFEST
[el contenido del manifiesto de arriba]

PRE-SUBMISSION CHECKLIST (lista de verificación previa al envío)
[la lista de arriba, con el estado actual de cada elemento]

SESSION NOTES UPDATE (actualización de las notas de sesión) (en cola, aún no aplicada)
- puestos objetivo activos > [target_id] > estado: "Packaged, awaiting submission"
- puestos objetivo activos > [target_id] > entregables: [rutas actualizadas]
- esta sesión > acciones de empaquetado: [lista]
- lecciones aprendidas: [entradas nuevas por añadir]

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- 10_interview_prep (para la preparación activa de la entrevista de este puesto)
- O bien: regrese al cierre del orquestador y luego al cierre de sesión del Módulo 12 (guarde sus archivos actualizados; si usa git, haga commit, opcional)
```

**Requisitos antialucinación:**
- No afirme que un archivo se creó o se movió a menos que la escritura o el movimiento haya ocurrido en realidad. Si la IA no puede escribir archivos en su configuración, produce el contenido completo de cada archivo y el usuario los guarda; verifique que los archivos existan antes de reportarlos como listos.
- No actualice las notas de sesión dentro de este módulo. Ponga en cola las actualizaciones para el lote de fin de sesión mediante el Módulo 12.
- La convención de nombres de archivo es estricta en ambas capas; no se desvíe solo porque un puesto suene a familia nueva. Proponga los nombres de familia nuevos de forma explícita.
- El manifiesto registra solo las decisiones realmente tomadas en esta construcción. No rellene secciones con contenido que suene plausible.

---

## Entregables esperados
- Archivos docx y PDF finales en `final/[nombre-del-puesto]/` (con nombre interno más copias con nombre de envío)
- HANDOFF_MANIFEST.md en la subcarpeta del puesto objetivo
- Metadatos de autor/creador establecidos y verificados
- Movimientos de archivado ejecutados para las versiones reemplazadas
- Cola de actualización de las notas de sesión (aplicada en el cierre de sesión del Módulo 12, con los archivos guardados después)

## Conexión con otros módulos
- Requiere PASS de `06_qa_gate` antes de ejecutarse
- Lee la guía de portales de `ats_upload_notes.md`
- El manifiesto lleva la clasificación según la tesis de carrera del Módulo 13 y las estimaciones de la calificación por rúbrica del Módulo 02
- Después del empaquetado: cierre del orquestador, o `10_interview_prep` si se necesita preparación para la entrevista
- El cierre de sesión del Módulo 12 aplica las actualizaciones en cola y el usuario guarda los archivos; ese guardado es el registro perdurable
- Los elementos de la lista de verificación del manifiesto que no se cumplan quedan marcados para la siguiente sesión
