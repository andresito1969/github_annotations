# github_annotations
Some github notes

# Useful commands
git commit -am 
git status -s
git reset --{soft, hard, mixed} HEAD~1
git commit --amend -m "Change prev git commit message"
git branch "new_branch" > git switch -c "new_branch" > git checkout -b "new_branch"
git switch "my_branch"

# HEAD
El head básicamente indica donde estamos actualmente, el HEAD puede ser los últimos cambios en nuestra rama o puede ser un checkout a un HASH commit previo que se haya hecho.

Entonces HEAD~1 indica del commit en el que stamos actualmente, señala el anterior y así hasta el infinito :D

# Git states
Changed, staged and commited
