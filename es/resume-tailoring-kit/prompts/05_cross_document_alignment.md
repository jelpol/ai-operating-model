# Módulo 05: Alineación entre documentos (05_cross_document_alignment)

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Tipo de módulo:** Pipeline + invocable
**Posición en el pipeline:** Módulo 5 de 15 (después de content_build y cover_letter_build, antes de qa_gate)
**Depende de:** Versión PRINT (para impresión), versión ATS (para el sistema de seguimiento de candidatos) y, si existe, la carta de presentación

## Qué hace este módulo
Audita las versiones PRINT, ATS y CoverLetter (carta de presentación) del mismo puesto para asegurar la consistencia del contenido. Detecta la deriva en fechas, títulos, métricas destacadas, entidades nombradas y afirmaciones fácticas. Las diferencias de tono entre formatos se aceptan; los desajustes fácticos son bloqueantes.

## Cuándo usarlo
- Después de content_build + cover_letter_build, antes de qa_gate
- De forma independiente siempre que existan varias versiones para el mismo puesto y se sospeche deriva
- Antes de cualquier envío final a un puesto objetivo

---

## PROMPT PARA PEGAR EN CLAUDE

Usted opera como **Módulo 05: Alineación entre documentos** para el sistema de adaptación de currículum del usuario.

Lea primero (asegúrese de que estos archivos estén pegados o adjuntos en este chat):
- `my-data/fact_registry.json`: fact_registry (registro de hechos), locked_framing_decisions (decisiones de encuadre bloqueadas), puesto objetivo activo
- `prompts/principles.md`: en especial el Principio #6 (alineación entre documentos)
- `prompts/semantic_equivalence_map.md`: para reconocer cuándo términos sinónimos entre documentos siguen siendo consistentes

Entradas:
- Versión PRINT (ruta de archivo o texto pegado)
- Versión ATS (ruta de archivo o texto pegado)
- (Opcional) Carta de presentación

**Verificaciones de alineación.**

Para cada par de documentos, ejecute estas verificaciones:

### 1. Fechas y títulos
- Las fechas de inicio y fin de cada puesto coinciden en todos los documentos
- El título de cada puesto coincide en todos los documentos
- Las fechas de la sección de trayectoria anterior (Earlier Career) coinciden donde aparecen los puestos

### 2. Métricas destacadas
- Conteo de reportes directos (por ejemplo, "[X]+" frente a "un puñado" = desalineación)
- Años de experiencia (por ejemplo, "[X]+ años" frente a "casi dos décadas"; señale si hay deriva)
- Conteo de proyectos, conteo de casos, escala del equipo
- Todas las afirmaciones de evidencia cuantificada

### 3. Entidades nombradas
- Descriptores de clientes mencionados (por ejemplo, "Fortune 100", "dependencias gubernamentales"; deben coincidir)
- Nombres de herramientas y plataformas (los ejemplos siguientes usan puestos de ciberseguridad, por ejemplo SailPoint, Entra ID; reconstruya las listas para el campo del usuario)
- Nombres de marcos y regímenes de cumplimiento (por ejemplo, SOX, ISO 27001; se menciona el mismo conjunto)
- Certificaciones listadas (deben ser idénticas entre los currículums; la carta de presentación no necesita listarlas, pero si lo hace, deben coincidir)

### 4. Decisiones de encuadre bloqueadas
Verifique contra la lista COMPLETA de locked_framing_decisions en su registro de hechos (my-data/fact_registry.json). Cada encuadre bloqueado debe respetarse de forma consistente en todos los documentos. Ejemplos (solo ilustrativos, no la lista completa):
- Trabajo de plataforma que el usuario apoyó pero que no estaba a su cargo = "en estrecha colaboración con los propietarios de la plataforma"
- Zero Trust = "contribuí a" o "codiseñé", nunca "implementé" sin matiz

### 5. Afirmaciones fácticas
Para cada afirmación sustantiva en un documento, verifique que cualquier afirmación relacionada en otro documento:
- No la contradiga
- No la exagere ni la minimice de manera significativa
- Use lenguaje semánticamente consistente (aplica semantic_equivalence_map.md)

### 6. Específico de la carta de presentación (cuando exista)
- Toda afirmación hecha en la carta de presentación debe estar respaldada por el contenido del currículum
- La carta de presentación no puede introducir experiencia que NO aparezca en el currículum
- Las brechas de credenciales reconocidas en la carta de presentación deben corresponder a la realidad (sin falsa humildad sobre credenciales que el usuario sí posee, sin falsa confianza sobre credenciales que no posee)

**Diferencias de tono aceptables (no se señalan):**
- La carta de presentación es conversacional; el currículum es directo
- La carta de presentación usa primera persona; el currículum usa primera persona implícita
- La carta de presentación explica "por qué este puesto"; el currículum no
- La carta de presentación puede nombrar un detalle específico de la empresa (por ejemplo, "el equilibrio entre rigor y pragmatismo en [Empresa]") que no aparecería en el currículum

**Estructura de salida:**

```
CROSS-DOCUMENT ALIGNMENT AUDIT (auditoría de alineación entre documentos): [Puesto objetivo]

DOCUMENTS COMPARED (documentos comparados):
- PRINT: [ruta]
- ATS: [ruta]
- Carta de presentación: [ruta o "N/A (no aplica)"]

ALIGNMENT STATUS (estado de alineación): [ALIGNED (alineado) / MINOR DRIFT (deriva menor) / BLOCKING MISALIGNMENT (desalineación bloqueante)]

DATES & TITLES (fechas y títulos)
- [PASS (aprobado): todo coincide / WARN (advertencia): deriva en ... / FAIL (fallo): desajuste en ...]

HEADLINE METRICS (métricas destacadas)
- [PASS: todo consistente / WARN: variación: [doc A: "X", doc B: "Y"]]

NAMED ENTITIES (entidades nombradas)
- [PASS: consistente / WARN: deriva: [detalles]]

LOCKED FRAMING DECISIONS (decisiones de encuadre bloqueadas; lista completa del registro de hechos)
- [PASS: respetadas / FAIL: violación: [doc: ..., texto: ..., bloqueo violado: ...]]

FACTUAL CLAIMS (afirmaciones fácticas)
- Total de afirmaciones comparadas: [N]
- Alineadas: [n]
- Deriva (semántica): [n]
- Contradicciones: [n]

COVER LETTER: RESUME BACKING (respaldo de la carta de presentación en el currículum; cuando exista la carta de presentación, CL)
- Afirmaciones en la CL: [n]
- Respaldadas por el currículum: [n]
- Sin respaldo en el currículum: [n]; deben resolverse

BLOCKING ISSUES (problemas bloqueantes; deben corregirse antes del envío)
1. [desajuste específico con referencias a los documentos]
2. ...

MINOR DRIFT (se recomienda corregir, no bloquea)
1. ...

RECOMMENDED NEXT MODULE (siguiente módulo recomendado)
- Si hay problemas bloqueantes: regresar a 04_content_build o a 08_cover_letter_build para resolverlos
- Si está limpio: 06_qa_gate
```

**Requisitos antialucinación:**
- No infiera alineación cuando los documentos realmente guardan silencio. Si un documento menciona "[N]+ casos" y otro no menciona casos en absoluto, eso no es una desalineación; es simplemente una ausencia.
- No fabrique deriva para parecer exhaustivo. Reporte solo diferencias reales.
- Cite el texto literal al reportar desajustes; no parafrasee la deriva aparente.

---

## Entregables esperados
- Estado de alineación (ALIGNED / MINOR DRIFT / BLOCKING MISALIGNMENT)
- Aprobado o fallo por verificación, con detalles específicos
- Lista de problemas bloqueantes (si los hay)
- Lista de deriva menor (recomendaciones)
- Siguiente módulo recomendado

## Conexión con otros módulos
- Si hay bloqueo: regresar a `04_content_build` o a `08_cover_letter_build`
- Si está limpio: `06_qa_gate`
- Patrones de deriva observados: anexar a `my-data/lessons_learned.md` (opcional) si son reutilizables
