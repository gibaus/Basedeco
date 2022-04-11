w : qui fait quoi ?
L'heure (aussi accessible via date)
L'uptime (aussi accessible via uptime)
La charge (aussi accessible via uptime et tload)
La liste des connectés (aussi accessible via who)

ps & top : lister les processus
ps : liste statique des processus
ps -ef : lister tous les processus
ps -ejH : afficher les processus en arbre
ps -u UTILISATEUR : lister les processus lancés par un utilisateur
top : liste dynamique des processus
	q : ferme top
	h : affiche l'aide, et donc la liste des touches utilisables.
	B : met en gras certains éléments.
	f : ajoute ou supprime des colonnes dans la liste.
	F : change la colonne selon laquelle les processus sont triés. En général, laisser le tri par défaut en fonction de %CPU est suffisant.
	u : filtre en fonction de l'utilisateur que vous voulez.
	k : tue un processus, c'est-à-dire arrête ce processus. Ne vous inquiétez pas, en général les processus ne souffrent pas. On vous demandera le numéro (PID) du processus que vous voulez tuer. Nous reviendrons sur l'arrêt des processus un peu plus loin.
	s : change l'intervalle de temps entre chaque rafraîchissement de la liste (par défaut, c'est toutes les trois secondes).

Ctrl + C & kill : arrêter un processus

kill : tuer un processus
	ps -u mateo21
	$ ps -u mateo21 | grep firefox
	32678 ?        00:00:03 firefox-bin
	kill 32678
	kill 32678 2768 33071

Avec kill -9 (comme le chiffre 9, oui, oui), vous demandez à Linux de tuer le processus 
sans lui laisser le temps de s'arrêter proprement. Cela peut faire le ménage quand rien ne va plus.

killall : tuer plusieurs processus
Contrairement à kill, killall attend le nom du processus à tuer et non son PID

halt & reboot : arrêter et redémarrer l'ordinateur
halt : arrêter l'ordinateur
reboot : redémarrer l'ordinateur

En résumé

    Linux est multi-tâches (plusieurs programmes peuvent tourner en même temps) et multi-utilisateurs (plusieurs utilisateurs peuvent se servir de la même machine en même temps en s'y connectant via Internet).

    w indique quels utilisateurs sont sur la machine, ce qu'ils font et quelques autres statistiques comme la charge de travail de la machine et son uptime.

    ps affiche la liste des processus, c'est-à-dire des programmes qui tournent sur la machine. top est un équivalent qui met à jour automatiquement la liste au fil du temps.

    La combinaison de touches Ctrl + C permet d'arrêter une commande en cours d'exécution dans la console afin de pouvoir reprendre la main.

    kill tue un processus, ce qui signifie qu'il lui demande de s'arrêter. Il a besoin du numéro du processus, généralement fourni par ps ou top. Si le processus ne s'arrête pas, on peut utiliser le paramètre -9 qui coupe brutalement le processus (avec risque de perte de données).

    halt commande l'arrêt de l'ordinateur, reboot son redémarrage.