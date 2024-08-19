### Git tips sacados del libor de midu

# FORK
Básicamente se crea otro repo que apunta al repo de origen, con lo cual no necesitamos permisos y 
podremos subir en nuestro nuevo repo aquello que querrámos.
Es útil porque podemos acabar haciendo pull request al repositorio original o en caso de nosotros querer 
extender el proyecto por ejemplo si estuviera deprecado, podríamos gracias a este mecanismo.

El funcionamiento es simple, vamos a un repo lo forkeamos y, luego vamos subiendo nuestros cambios y, actualizando 
si queremos nuestra rama main con el repo original, para acabar haciendo una pull request, en el repo de origen.

# New Useful commands
git commit -am 
git status -s
git reset --{soft, hard, mixed} HEAD~1
git commit --amend -m "Change prev git commit message"
git branch "new_branch" > git switch -c "new_branch" > git checkout -b "new_branch"
git switch "my_branch"

# FLOWS (Pull request)
Básicamente hay varias formas de trabajar en git, las más conocidas son:
  * Git flow (Crear una rama main y otra de testing + ramas support que parten de main
    y se van subiendo a testing, en caso de funcionar esas ramas pasan a main), forma arcaica.
    
  * Github flow / PR flow (Trabajamos sobre una rama main y ramas support que vayamos creando,
    esas ramas una vez están a punto, se va solicitando su pull request, la cual puede ser aceptada por personas del equipo).
  
  * Trunk Based Development (Trabajar sobre una única rama y, directamente ir subiendo los cambios)
  * Ship show ask (Combinación entre PR flow y Trunk Based Development, podemos shippear es decir pasar directamente los cambios
    sin preguntar a nadie, podemos hacer un show crear una PR pero autoaceptarla para que quede constancia o ask que sería
    el funcionamiento normal de las PR)

Ambos tienen sus ventajas y desventajas, para poner algo de contexto el trunk based development aunque suene contraintuitivo suele usarse mucho
en equipos muy maduros y con un nivel elevado, ya que puede ser algo peligroso en equipos que gozan de una menor experiencia.

Para equipos con menos experiencia es más recomendado Github flow / PR flow.

# Buenas prácticas
 * Enviar un mensaje de commit conciso y explicativo, con un prefijo que indique (Test, development, feature, bugfix etc).
 * Nombres de ramas lo más elegante posible.
 * No hacer monster commit (anti patrón) e ir haciendo commit constantemente para que sea fácil de seguir.
 * No llenar los repos de muchas ramas en el origin.
 * De usar gitflow nunca partir de la rama testing ni ninguna otra a menos que se tenga conocimiento, partir siempre de main.
 * Hacer uso de gitignore para no subir mucha "mierda"
 * Revisar cada commit hecho e intentar limpiar "basura" como espacios extra y etc (esto puede ser arreglado con un linter genérico)
 * Intentar automatizar tareas a la hora de integrar, por ejemplo en caso de que se acepte código malicioso, hacer un revert de este
   mediante github actions o jenkins por ejemplo.

# HEAD
El head básicamente indica donde estamos actualmente, el HEAD puede ser los últimos cambios en nuestra rama 
o puede ser un checkout a un HASH commit previo que se haya hecho.

Entonces HEAD~1 indica del commit en el que stamos actualmente, señala el anterior y así hasta el infinito :D

# Git states
Changed, staged and commited

# TIPS
En el libro de midu, hay varias páginas donde podemos acceder a proyectos que requieran de ayuda de la comunidad.
También es importante contrubuir ya que es una forma de agradecer por tanto código y recursos gratis
que hemos consumido en toda nuestra vida.
También la otra es que nos aumenta muchísimo el nivel, ya que otras personas revisarán nuestros códigos
y, nosotros también.


# Flow de un proyecto que puede ser interesante.
Clonar o forkar + clonar el repositorio del proyecto.
Una vez lo tenemos en local, a partir de la rama principal (main) creamos una rama para poner nuestros cambios.
 - git switch -c "nueva_rama" // Donde nueva rama es el nombre, de nuestra rama, tiene que ser autoexplicativa por ejemplo podría ser "correccion_pantalla_login"

Mientras trabajamos en nuestra rama, podemos hacer los siguientes comandos:
 - git add .
 - git commit -m "BUGFIX Se ha corregido el login, error de compatibilidad en edge"
 - git push (este comando no hace falta, a menos que querrámos ir actualizando la rama y que esta esté en el repositorio origin (es decir la nube) o que se trabaje con pull request)

Una vez hemos acabado de realizar todos los cambios en la rama para poderla pasar a main:
 - git switch main
 - git fetch && git pull (Esto obtiene cambios del origin y hace un pull de estos)
 - git merge "correccion_pantalla_login"
 - git push

Y ya tendríamos los cambios pasados.


En el caso de ser un clone, directamente al tener permisos ya aparecerán los cambios en nuestro equipo de desarrolladores.
Si es un fork, deberemos realizar la pull request en el repositorio original desde github gitlab o el que usemos, y esperar a que nos la acepten.

En el caso de trabajar con PR flow o ship/show/ask, dependerá si es un ask/show deberemos no mergear contra main y, subir la rama y realizar una pull request.
Si es un ship, directamente el merge a main y repetir lo explicado.
