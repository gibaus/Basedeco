"&" & nohup : lancer un processus en arri�re-plan
& : lancer un processus en arri�re-plan
	cp video.avi copie_video.avi &
	[1] 16504
    [1] : c'est le num�ro du processus en arri�re-plan dans cette console. 
Comme c'est le premier processus que nous envoyons en arri�re-plan, il prend le num�ro 1.
    16504 : c'est le num�ro d'identification g�n�ral du processus (le fameux PID dont on a d�j� parl�).
Cette information vous permet de tuer le processus avec kill si n�cessaire.

	find / -name "*log" > sortiefind &
	[1] 18191
	$ find / -name "*log" > sortiefind 2>&1 &
	[1] 18231

nohup : d�tacher le processus de la console
	
	$ nohup cp video.avi copie_video.avi
	nohup: ajout � la sortie de `nohup.out'

Ctrl + Z, jobs, bg & fg : passer un processus en arri�re-plan
Ctrl + Z : mettre en pause l'ex�cution du programme
bg : passer le processus en arri�re-plan (background)
jobs : conna�tre les processus qui tournent en arri�re-plan
fg : reprendre un processus au premier plan (foreground)

screen : plusieurs consoles en une

En r�sum�

    Il est possible d'envoyer des programmes en arri�re-plan dans la console afin de garder la main pour lancer de nouvelles commandes.

    Pour lancer un processus en arri�re-plan, on peut ajouter le symbole & � la fin de la commande. En revanche, lorsque vous fermez la console, le processus est arr�t�. Si vous voulez qu'il continue, utilisez plut�t la commande nohup.

    Si vous avez lanc� une commande normalement (en avant-plan) mais que celle-ci s'�ternise, vous pouvez utiliser le raccourci Ctrl + Z pour la mettre en pause et r�cup�rer la main. Si vous lancez la commande bg ensuite, elle reprendra son ex�cution en arri�re-plan. Vous pourrez la r�cup�rer au premier plan avec fg � tout moment.

    screen est un programme puissant que vous pouvez installer avec apt-get (il n'est pas pr�sent par d�faut). Il permet d'ouvrir plusieurs consoles virtuelles au sein d'une seule et m�me console, et donc d'ex�cuter facilement plusieurs processus en parall�le.

    #



