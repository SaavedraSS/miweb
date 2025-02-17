chanchito feliz

# Flujo de trabajo de Git
computadora -> Stage -> commit -> server (opcional)

# Inicializar un repositorio
Después de acceder a la carpeta que contiene nuestra proyecto, ejecutamos el comando:
- git init

# Comandos de git bash:
- git config --global -e: abre el archivo de configuración global en el editor predeterminado.
- code .: abre la carpeta actual desde el editor predeterminado.
- ls: permite mostrar una lista de los archivos y carpetas dentro de la carpeta actual
-pwd: indica la carpeta actual
- cd <carpeta>: permite acceder a una carpeta que se encuentra dentro de la carpeta actual
- cd .. : permite retroceder una carpeta de la actual.
- mkdir <nomre-nuevo-directorio>: crea una nueva carpeta en la carpeta actual.

- git status: muestra el estado actual de los archivos (la etapa de 'stage'). Si se ha modificado, borrado o agregado algo.
- git status -s: muestra el estado actual de los archivos de manera abreviada.
    - Colores de cada símbolo
        - Rojo: cambios en el directorio de trabajo. No en 'stage'
        - Verde: cambios en el 'stage'
    - ??: archivo no ratreado
    - A: Archivo recién añadido al 'stage'
    - M: Archivo modificado
    - D: Eliminado
    - R: Renombrado
    - U: Conflicto de fusión
    - AM: Archivo añadido al 'stage', pero modificado nuevamente en el directorio



- git add <file>: permite agregar un cambio en el repositorio en el 'stage'. se realiza mediante le nombre del archivo.
    de esta manera git puede seguir el rastro del archivo.
- cat <file>: muestra el contenido del archivo.
- git commit -m "<mensaje sobre el commit>": permite agregar un commit

## Eliminar y restaurar archivos
- rm <file>: borrar archivo. no lo agrega al 'stage'
- git rm <file>: borra y agrega la eliminación del archivo al 'stage'
- git restore --staged <file>: restaura el cambio del 'stage'
- git restore <file>: restaura el cambio.

## Cambiando de nombre
- mv <file> <new_name_file>: cambiar de nombre un archivo. mv comando mover.
    Esto borra el archivo y crea otro con el nombre especificado.
- git add <file> <new_name_file>: agrega ambos cambios (creación y eliminación) al 'stage'
- git mv <file> <new_name_file>: renombra un archivo y lo agrega al 'stage'

# Ignorando archivos y carpetas
Se usa para evitar que accidentalmente se suban archivos al servidor.
Se crea un archivo .gitignore y dentro colocamos los archivos y carpetas a ignorar

# Visualizando todos los cambios
- git diff: cambios que se han hecho en la computadora, sin ser agregados al 'stage', en cada línea de los archivos.
- git diff --staged: cambios que se encuentran en la etapa de 'stage'

# Mostrar el historial de los commits
- git log: Muestra el identificador del commit junto al autor y su correo, fecha y mensaje.
    el historial se muestra en un visor.
    - Barra espaciadora: Avanza una página hacia abajo.
    - b: Retrocede una página hacia arriba.
    - Enter: Avanza una línea hacia abajo.
    - / + texto + Enter: Busca un texto específico en el historial.
    - q: Sale del visor (como ya mencionamos).
- git log --oneline: Forma resumida. Muestra un identificador junto al mensaje de cada commit

# Ramas (branches)
- git branch: muestra todas las ramas. Se muestra un asterisco en la rama en la que estamos trabajando actualmente.
- git branch <nombre-de-nueva-rama>: crea una nueva rama, sin cambiarse a esa.
- git branch -d <nombre-rama-eliminar>: Elimina una rama

- git checkout -b <nombre-de-nueva-rama>: crea una nueva rama y se cambia a ella.
- git checkout <nombre-de-rama-a-cambiar>: cambia de rama

# Uniendo Ramas
Desde la rama a la cual se queremos acoplar, se ejecuta el comando:
- git merge <rama-a-acoplar>

# Subir los commits al server (GitHub)
- git push
- git push -u origin <rama-a-subir-en-repositorio>: sube una rama al repositorio