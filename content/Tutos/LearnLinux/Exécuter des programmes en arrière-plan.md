"&" & nohup : lancer un processus en arrière-plan
& : lancer un processus en arrière-plan
	cp video.avi copie_video.avi &
	[1] 16504
    [1] : c'est le numéro du processus en arrière-plan dans cette console. 
Comme c'est le premier processus que nous envoyons en arrière-plan, il prend le numéro 1.
    16504 : c'est le numéro d'identification général du processus (le fameux PID dont on a déjà parlé).
Cette information vous permet de tuer le processus avec kill si nécessaire.

	find / -name "*log" > sortiefind &
	[1] 18191
	$ find / -name "*log" > sortiefind 2>&1 &
	[1] 18231

nohup : détacher le processus de la console
	
	$ nohup cp video.avi copie_video.avi
	nohup: ajout à la sortie de `nohup.out'

Ctrl + Z, jobs, bg & fg : passer un processus en arrière-plan
Ctrl + Z : mettre en pause l'exécution du programme
bg : passer le processus en arrière-plan (background)
jobs : connaître les processus qui tournent en arrière-plan
fg : reprendre un processus au premier plan (foreground)

screen : plusieurs consoles en une

En résumé

    Il est possible d'envoyer des programmes en arrière-plan dans la console afin de garder la main pour lancer de nouvelles commandes.

    Pour lancer un processus en arrière-plan, on peut ajouter le symbole & à la fin de la commande. En revanche, lorsque vous fermez la console, le processus est arrêté. Si vous voulez qu'il continue, utilisez plutôt la commande nohup.

    Si vous avez lancé une commande normalement (en avant-plan) mais que celle-ci s'éternise, vous pouvez utiliser le raccourci Ctrl + Z pour la mettre en pause et récupérer la main. Si vous lancez la commande bg ensuite, elle reprendra son exécution en arrière-plan. Vous pourrez la récupérer au premier plan avec fg à tout moment.

    screen est un programme puissant que vous pouvez installer avec apt-get (il n'est pas présent par défaut). Il permet d'ouvrir plusieurs consoles virtuelles au sein d'une seule et même console, et donc d'exécuter facilement plusieurs processus en parallèle.

    #



