# github_annotations
Some github notes

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
