# Cargador de espacio de trabajo (workspace), plantilla

*Edición en español (México), traducida de la versión inglesa en el commit 40494f3. La versión en inglés es la canónica.*

Guarde este archivo como `CLAUDE.md` dentro de la carpeta del espacio de
trabajo. Es deliberadamente delgado. Se carga solo cuando la IA toca esta
carpeta, incorpora la doctrina completa mediante imports y enuncia los
rituales. El detalle vive en los archivos importados, nunca aquí, de modo
que la capa global de carga permanente se mantiene ligera y este cargador
conserva cada dominio autocontenido.

```markdown
# Cargador de <Nombre del workspace>

<Una línea: qué es este espacio de trabajo y sus alias cotidianos.> Se carga
bajo demanda cuando la IA toca archivos en esta carpeta. El control de
versiones es la fuente de verdad; los archivos canónicos se editan en su
lugar y el historial es el registro.

@WORKSPACE_INDEX.md
@<archivo de doctrina, p. ej. operating-model.md o principles.md>

## Inicio de sesión
Lea el índice y luego el archivo de State más reciente por fecha.
Concilie el estado con el humano antes de actuar. "¿Ha cambiado algo que el
registro no refleje?"

## <El ciclo operativo del workspace>
<Dos o tres líneas. Los modos, el ciclo o el pipeline que este espacio de
trabajo ejecuta. Señale el archivo de doctrina para el detalle.>

## Cierre
Actualice el registro de State. Encauce las lecciones según el ciclo de
aprendizaje, incluida la bandeja de entrada entre dominios para las
lecciones a nivel de sistema. El commit y el push son el registro
duradero. Una sesión que cambie algo termina con ambos.
```

Los archivos complementarios que este cargador espera son `WORKSPACE_INDEX.md`
(el mapa de una página que cubre propósito, estructura, archivos
canónicos y ritual), el archivo de doctrina (construido a partir de la
plantilla del esqueleto) y una carpeta `State/` que contiene registros
fechados, con el más reciente como el vigente.
