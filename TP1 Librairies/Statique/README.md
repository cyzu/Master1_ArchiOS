
## Création d'une librairie statique :
	gcc -c code.c -o code.o
	ar rcs libcode.a code.o    //r (insert .o into library), c (create library), s (insert table d'index)
	nm libcode.a               // information sur la lib

## Compilation :
	gcc exec.c -L . -lcode -o exec
  
        /* -L insertion des librairies
          .  dans le rep courant (chemin)
          .. si dans le rep mère 
           $PATH le chemin sinon
        */ 
    
## Execution :
	./exec


La librairie se trouve dans l'executable donc le programme fonctionne même après suppression de la *librairie.a* .

La mise à jour de la librairie n'est pas automatique, il faut recompiler depuis *ar* pour la mettre à jour.
