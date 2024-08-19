# github_annotations
Some github notes

# FORK
Básicamente se crea otro repo que apunta al repo de origen, con lo cual no necesitamos permisos y 
podremos subir en nuestro nuevo repo aquello que querrámos.
Es útil porque podemos acabar haciendo pull request al repositorio original o en caso de nosotros querer 
extender el proyecto por ejemplo si estuviera deprecado, podríamos gracias a este mecanismo.

El funcionamiento es simple, vamos a un repo lo forkeamos y, luego vamos subiendo nuestros cambios y, actualizando 
si queremos nuestra rama main con el repo original, para acabar haciendo una pull request, en el repo de origen.

# Useful commands
git commit -am 
git status -s
git reset --{soft, hard, mixed} HEAD~1
git commit --amend -m "Change prev git commit message"
git branch "new_branch" > git switch -c "new_branch" > git checkout -b "new_branch"
git switch "my_branch"

# HEAD
El head básicamente indica donde estamos actualmente, el HEAD puede ser los últimos cambios en nuestra rama 
o puede ser un checkout a un HASH commit previo que se haya hecho.

Entonces HEAD~1 indica del commit en el que stamos actualmente, señala el anterior y así hasta el infinito :D

# Git states
Changed, staged and commited

