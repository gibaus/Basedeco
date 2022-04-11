w : qui fait quoi ?
L'heure (aussi accessible via date)
L'uptime (aussi accessible via uptime)
La charge (aussi accessible via uptime et tload)
La liste des connect�s (aussi accessible via who)

ps & top : lister les processus
ps : liste statique des processus
ps -ef : lister tous les processus
ps -ejH : afficher les processus en arbre
ps -u UTILISATEUR : lister les processus lanc�s par un utilisateur
top : liste dynamique des processus
	q : ferme top
	h : affiche l'aide, et donc la liste des touches utilisables.
	B : met en gras certains �l�ments.
	f : ajoute ou supprime des colonnes dans la liste.
	F : change la colonne selon laquelle les processus sont tri�s. En g�n�ral, laisser le tri par d�faut en fonction de %CPU est suffisant.
	u : filtre en fonction de l'utilisateur que vous voulez.
	k : tue un processus, c'est-�-dire arr�te ce processus. Ne vous inqui�tez pas, en g�n�ral les processus ne souffrent pas. On vous demandera le num�ro (PID) du processus que vous voulez tuer. Nous reviendrons sur l'arr�t des processus un peu plus loin.
	s : change l'intervalle de temps entre chaque rafra�chissement de la liste (par d�faut, c'est toutes les trois secondes).

Ctrl + C & kill : arr�ter un processus

kill : tuer un processus
	ps -u mateo21
	$ ps -u mateo21 | grep firefox
	32678 ?        00:00:03 firefox-bin
	kill 32678
	kill 32678 2768 33071

Avec kill -9 (comme le chiffre 9, oui, oui), vous demandez � Linux de tuer le processus 
sans lui laisser le temps de s'arr�ter proprement. Cela peut faire le m�nage quand rien ne va plus.

killall : tuer plusieurs processus
Contrairement � kill, killall attend le nom du processus � tuer et non son PID

halt & reboot : arr�ter et red�marrer l'ordinateur
halt : arr�ter l'ordinateur
reboot : red�marrer l'ordinateur

En r�sum�

    Linux est multi-t�ches (plusieurs programmes peuvent tourner en m�me temps) et multi-utilisateurs (plusieurs utilisateurs peuvent se servir de la m�me machine en m�me temps en s'y connectant via Internet).

    w indique quels utilisateurs sont sur la machine, ce qu'ils font et quelques autres statistiques comme la charge de travail de la machine et son uptime.

    ps affiche la liste des processus, c'est-�-dire des programmes qui tournent sur la machine. top est un �quivalent qui met � jour automatiquement la liste au fil du temps.

    La combinaison de touches Ctrl + C permet d'arr�ter une commande en cours d'ex�cution dans la console afin de pouvoir reprendre la main.

    kill tue un processus, ce qui signifie qu'il lui demande de s'arr�ter. Il a besoin du num�ro du processus, g�n�ralement fourni par ps ou top. Si le processus ne s'arr�te pas, on peut utiliser le param�tre -9 qui coupe brutalement le processus (avec risque de perte de donn�es).

    halt commande l'arr�t de l'ordinateur, reboot son red�marrage.