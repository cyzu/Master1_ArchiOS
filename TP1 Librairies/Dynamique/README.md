
## Création librairie dynamique :
	gcc -c -fPIC code.c -o code.o     /* -fPIC (Position Independent Code) */
	gcc -shared -o libcode.so code.o

## Compilation :
	gcc exec.c -L . -lcode -o exec

:warning: Ne fonctionnera pas à cette étape car l'executable ne connait pas la chemin de la librairie *(LD_LIBRARY_PATH)*.

## Set LD_LIBRARY_PATH :
	LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/user/.../last_repository
	export LD_LIBRARY_PATH

## Execution :
	./exec

Lien créé entre le code et la librairie dynamique.

On peut déplacer l'executable dans un autre fichier, puis lancer le programme sans rien changer.

## Mise à jour de la librairie :
	  - Refaire la création
	  - Execution
