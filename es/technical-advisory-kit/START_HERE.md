# Empiece aquí

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

Este kit hace que un asistente de IA sea útil para trabajo técnico real: estudiar material hasta manejarlo con verdadera competencia y revisar diseños sin que la IA lo halague. Se construyó y se probó en condiciones reales dentro de una práctica de seguridad en operación, y después se le retiraron los datos del propietario para que cualquiera pueda ejecutarlo.

Supone que usted trabaja en un campo técnico o cerca de uno. Si el kit de currículum vecino trata de conseguir el empleo, este trata de ser bueno en él.

## Las dos reglas que hacen que esto funcione

1. **La IA nunca responde de memoria sobre nada que cambie.** Versiones, funciones, licenciamiento, CVE, identificadores de marcos: se verifican en vivo o se etiquetan como no verificados. El Módulo 03 lo hace cumplir durante toda una sesión de chat.
2. **Usted lleva el registro de lo que realmente sabe.** El registro de conocimientos es un mapa honesto de sus dominios de experto, su competencia funcional y sus brechas abiertas nombradas. La IA lo lee y se calibra: no vuelve a enseñar lo que usted domina ni supone una profundidad que usted no tiene. Las sesiones de estudio existen para mover elementos de una categoría a otra dentro de ese mapa, y el entregable es la lista de brechas, no la lectura.

## Sesión 1: configuración (20 minutos)

1. Copie `templates/knowledge_registry_template.md` a `my-data/knowledge_registry.md` y llénelo con honestidad. Inflar la lista de dominios de experto provoca que reciba respuestas equivocadas sin verificar justo en los lugares donde menos puede permitírselas.
2. Hojee `prompts/principles.md` para conocer las reglas permanentes.
3. Cree las carpetas `my-data/learnings/` y `my-data/validations/`. **`my-data/` permanece privada, siempre.**

## Cada sesión de trabajo posterior

1. Abra un chat de IA y pegue primero `prompts/03_verification_gate.md`. Gobierna cada respuesta durante el resto del chat.
2. ¿Está estudiando algo? Pegue `prompts/01_research_anchoring.md` más el material más su registro. Guarde el artefacto de cinco salidas en `my-data/learnings/` y agregue las filas de brechas nuevas a su registro.
3. ¿Está decidiendo algo? Pegue `prompts/02_validate_a_design.md` más el diseño. Sólido (Sound), Sólido con salvedades (Sound with caveats) o Defectuoso (Flawed), calificado en modos de falla, superficie de ataque, escala, operación, costo y cumplimiento. Conserve el veredicto en `my-data/validations/` si su yo del futuro lo va a citar.
4. Cierre actualizando el registro si su nivel cambió.

## Mensualmente, quince minutos

Vuelva a revisar todo aquello cuya fecha de vencimiento haya pasado, concilie contradicciones y confirme que el registro sigue correspondiendo a la realidad. Si omite esto, la base de conocimientos se degrada en silencio.

## Privacidad

El mismo trato que en todos los kits de aquí: los prompts son públicos, sus datos no. Su registro es un mapa de sus fortalezas y debilidades profesionales; sus aprendizajes pueden hacer referencia al entorno de su empleador. `my-data/` se entrega vacía y excluida de git mediante .gitignore. Pegar un registro en un chat de IA lo envía a ese proveedor, así que use uno en el que confíe y revise su configuración de retención.
