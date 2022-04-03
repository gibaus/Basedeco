Le #! est appelé le sha-bang, (on écrit aussi shebang, mais on utilisera "sha-bang" dans ce cours).
/bin/bash peut être remplacé par /bin/sh si vous souhaitez coder pour sh, /bin/ksh pour ksh, etc.

Installer un nouveau shell
apt-get install ksh
chsh
chsh signifie Change Shell.
On vous demandera où se trouve le programme qui gère le shell. Vous devrez indiquer /bin/ksh pour ksh, /bin/sh pour sh, /bin/bash pour bash, etc.

Or, pour exécuter un script, il faut que le fichier ait le droit « exécutable ». Le plus simple pour donner ce droit est d'écrire :
 chmod +x essai.sh

 Le script s'exécute maintenant comme n'importe quel programme, en tapant « ./ » devant le nom du script :

$ ./essai.sh
essai.sh

Exécution de débogage
bash -x essai.sh

En résumé

    Contrairement aux apparences, il existe plusieurs environnements console différents : ce sont les shells. Ce sont eux qui gèrent l'invite de commandes et ses fonctionnalités comme l'historique des commandes, la recherche Ctrl + R, l'autocomplétion des commandes…

    Le shell utilisé par défaut sous Ubuntu est bash, mais il existe aussi ksh, zsh, etc.

    Il est possible d'automatiser une série de commandes. On crée pour cela un fichier contenant la liste des commandes à exécuter, appelé script shell. On dit que l'on fait de la programmation shell.

    En fonction du shell utilisé, on dispose de différents outils pour créer son script shell. Nous utiliserons ici bash, donc notre fichier de script doit commencer par la ligne #!/bin/bash.

    Dans le fichier de script, il suffit d'écrire les commandes à exécuter les unes après les autres, chacune sur une ligne différente.

    Pour exécuter le script (et donc exécuter la liste des commandes qu'il contient) il faut donner les droits d'exécution au fichier (chmod +x script.sh) et lancer l'exécution du script avec la commande ./script.sh.



   echo : afficher une variable
        Si vous voulez insérer des retours à la ligne, il faudra activer le paramètre -e et utiliser le symbole \n :
        $ echo -e "Message\nAutre ligne"
        Message
        Autre ligne

        Afficher une variable
        #!/bin/bash

        message='Bonjour tout le monde'
        echo $message

        #!/bin/bash

        message='Bonjour tout le monde'
        echo 'Le message est : $message'

        Le message est : $message

        Les simples quotes ' '

Commençons par les simples quotes :

message='Bonjour tout le monde'
echo 'Le message est : $message'

Le message est : $message

Avec de simples quotes, la variable n'est pas analysée et le $ est affiché tel quel.
Les doubles quotes " "

Avec des doubles quotes :

message='Bonjour tout le monde'
echo "Le message est : $message"

Le message est : Bonjour tout le monde

… ça fonctionne ! Cette fois, la variable est analysée et son contenu affiché.

Les back quotes ` `

Un peu particulières, les back quotes demandent à bash d'exécuter ce qui se trouve à l'intérieur.

message=`pwd`
echo "Vous êtes dans le dossier $message"

Vous êtes dans le dossier /home/mateo21/bin



read : demander une saisie
-p : afficher un message de prompt
        #!/bin/bash

        read -p 'Entrez votre nom : ' nom
        echo "Bonjour $nom !"

Affecter simultanément une valeur à plusieurs variables
        #!/bin/bash

        read nom prenom
        echo "Bonjour $nom $prenom !"

        Deschamps Mathieu
        Bonjour Deschamps Mathieu !

read lit ce que vous tapez mot par mot (en considérant que les mots sont séparés par des espaces). Il assigne chaque mot à une variable différente, d'où le fait que le nom et le prénom ont été correctement et respectivement assignés à $nom et $prenom.
Si vous rentrez plus de mots au clavier que vous n'avez prévu de variables pour en stocker, la dernière variable de la liste récupèrera tous les mots restants. En clair, si j'avais tapé pour le programme précédent « Nebra Mathieu Cyril », la variable $prenom aurait eu pour valeur
-p : afficher un message de prompt
        #!/bin/bash

        read -p 'Entrez votre nom : ' nom
        echo "Bonjour $nom !"
        Résultat :
        Entrez votre nom : Mathieu
        Bonjour Mathieu !
-n : limiter le nombre de caractères
-t : limiter le temps autorisé pour saisir un message
-s : ne pas afficher le texte saisi

Effectuer des opérations mathématiques
let
        #!/bin/bash

        let "b = 2"
        let "c = a + b"
        echo $c
Les opérations utilisables sont :
    l'addition : + ;
    la soustraction : - ;
    la multiplication : * ;
    la division : / ;
    la puissance : ** ;
    le modulo (renvoie le reste de la division entière) : %.

    let "a = 5 * 3" # $a = 15
    let "a = 4 ** 2" # $a = 16 (4 au carré)
    let "a = 8 / 2" # $a = 4
    let "a = 10 / 3" # $a = 3
    Une petite explication pour les deux dernières lignes :
    10 / 3 = 3 car la division est entière (la commande ne renvoie pas de nombres décimaux) ;
    10 % 3 renvoie 1 car le reste de la division de 10 par 3 est 1. En effet, 3 « rentre » 3 fois dans 10 (ça fait 9), et il reste 1 pour aller à 10.

Actuellement, les résultats renvoyés sont des nombres entiers et non des nombres décimaux. Si vous voulez travailler avec des nombres décimaux, renseignez-vous sur le fonctionnement de la commande bc

Les variables d'environnement
env

        $ env
        ORBIT_SOCKETDIR=/tmp/orbit-mateo21
        GLADE_PIXMAP_PATH=:/usr/share/glade3/pixmaps
        TERM=xterm
        SHELL=/bin/bash
        GTK_MODULES=canberra-gtk-module
        USER=mateo21
        PATH=/home/mateo21/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin: /usr/bin:/sbin:/bin:/usr/games
        GDM_XSERVER_LOCATION=local
        PWD=/home/mateo21/bin
        EDITOR=nano
        SHLVL=1
        HOME=/home/mateo21
        OLDPWD=/home/mateo21

        [ ... ]

SHELL : indique quel type de shell est en cours d'utilisation (sh, bash, ksh…) ;

PATH : une liste des répertoires qui contiennent des exécutables que vous souhaitez pouvoir lancer sans indiquer leur répertoire. Nous en avons parlé un peu plus tôt. Si un programme se trouve dans un de ces dossiers, vous pourrez l'invoquer quel que soit le dossier dans lequel vous vous trouvez ;

EDITOR : l'éditeur de texte par défaut qui s'ouvre lorsque cela est nécessaire ;

HOME : la position de votre dossier home ;

PWD : le dossier dans lequel vous vous trouvez ;

OLDPWD : le dossier dans lequel vous vous trouviez auparavant.

Les variables des paramètres
En effet, des variables sont automatiquement créées :

    $# : contient le nombre de paramètres ;

    $0 : contient le nom du script exécuté (ici ./variables.sh) ;

    $1 : contient le premier paramètre ;

    $2 : contient le second paramètre ;

    … ;

    $9 : contient le 9e paramètre.

Essayons :

        #!/bin/bash

        echo "Vous avez lancé $0, il y a $# paramètres"
        echo "Le paramètre 1 est $1"

Les tableaux
    tableau=('valeur0' 'valeur1' 'valeur2')
    ${tableau[2]}

En résumé

    Comme dans la plupart des langages de programmation, on peut créer des variables en shell qui stockent temporairement des valeurs en mémoire. Une variable nommée variable est accessible en écrivant $variable.

    La commande echo affiche un texte ou le contenu d'une variable dans la console.

    read attend une saisie au clavier de la part de l'utilisateur et stocke le résultat dans une variable.

    On peut effectuer des opérations mathématiques sur des nombres à l’aide de la commande let.

    Certaines variables sont accessibles partout, dans tous les scripts : ce sont les variables d'environnement. On peut les lister avec la commande env.

    Les paramètres envoyés à notre script (comme ./script -p) sont transmis dans des variables numérotées : $1, $2, $3… Le nombre de paramètres envoyés est indiqué dans la variable $#.

Les conditions
if : la condition la plus simple
    SI test_de_variable
    ALORS
    ------> effectuer_une_action
    FIN SI

La syntaxe en bash est la suivante :

    if [ test ]
    then
            echo "C'est vrai"
    fi
Vous noterez — c'est très important — qu'il y a des espaces à l'intérieur des crochets. On ne doit pas écrire[test]mais[ test ] !
Sinon
Si vous souhaitez faire quelque chose de particulier quand la condition n'est pas remplie, vous pouvez rajouter unelsequi signifie « sinon ».
En français, cela s'écrirait comme ceci :

SI test_de_variable
ALORS
------> effectuer_une_action
SINON
------> effectuer_une_action
FIN SI

        #!/bin/bash

        if [ $1 = "Bruno" ]
        then
                echo "Salut Bruno !"
        else
                echo "J'te connais pas, ouste !"
        fi

Sinon si

Il existe aussi le mot cléelif, abréviation de « else if », qui signifie « sinon si ». Sa forme ressemble à ceci :

SI test_de_variable
ALORS
------> effectuer_une_action
SINON SI autre_test
ALORS
------> effectuer_une_action
SINON SI encore_un_autre_test
ALORS
------> effectuer_une_action
SINON
------> effectuer_une_action
FIN SI

        if [ test ]
        then
                echo "Le premier test a été vérifié"
        elif [ autre_test ]
        then
                echo "Le second test a été vérifié"
        elif [ encore_autre_test ]
        then
                echo "Le troisième test a été vérifié"
        else
                echo "Aucun des tests précédents n'a été vérifié"
        fi

Les tests
Il est possible d’effectuer trois types de tests différents en bash :

    des tests sur des chaînes de caractères ;
    des tests sur des nombres ;
    des tests sur des fichiers.

Tests sur des chaînes de caractères

$chaine1 = $chaine2
Vérifie si les deux chaînes sont identiques. Notez que bash est sensible à la casse : « b » est donc différent de « B ».
Il est aussi possible d'écrire « == » pour les habitués du langage C.

$chaine1 != $chaine2
Vérifie si les deux chaînes sont différentes.

-z $chaine
Vérifie si la chaîne est vide.

-n $chaine
Vérifie si la chaîne est non vide.

Tests sur des nombres

$num1 -eq $num2


Vérifie si les nombres sont égaux (equal). À ne pas confondre avec le « = » qui, lui, compare deux chaînes de caractères.

$num1 -ne $num2
Vérifie si les nombres sont différents (nonequal).
Encore une fois, ne confondez pas avec « != » qui est censé être utilisé sur des chaînes de caractères.

$num1 -lt $num2
Vérifie sinum1est inférieur ( < ) ànum2(lowerthan).

$num1 -le $num2
Vérifie sinum1est inférieur ou égal ( <= ) ànum2(lowerorequal).

$num1 -gt $num2
Vérifie sinum1est supérieur ( > ) ànum2(greaterthan).

$num1 -ge $num2
Vérifie sinum1est supérieur ou égal ( >= ) ànum2(greaterorequal).

Tests sur des fichiers

-e $nomfichier
Vérifie si le fichier existe.

-d $nomfichier
Vérifie si le fichier est un répertoire. N'oubliez pas que sous Linux, tout est considéré comme un fichier, même un répertoire !

-f $nomfichier
Vérifie si le fichier est un… fichier. Un vrai fichier cette fois, pas un dossier.

-L $nomfichier
Vérifie si le fichier est un lien symbolique (raccourci).

-r $nomfichier
Vérifie si le fichier est lisible (r).

-w $nomfichier
Vérifie si le fichier est modifiable (w).

-x $nomfichier
Vérifie si le fichier est exécutable (x).

$fichier1 -nt $fichier2
Vérifie sifichier1est plus récent quefichier2(newerthan).

$fichier1 -ot $fichier2
Vérifie sifichier1est plus vieux quefichier2(olderthan).

Effectuer plusieurs tests à la fois
Dans unif, il est possible de faire plusieurs tests à la fois. En général, on vérifie :

    si un test est vrai ET qu'un autre test est vrai ;

    si un test est vrai OU qu'un autre test est vrai.

Les deux symboles à connaître sont :

    && : signifie « et » ;

    || : signifie « ou ».

Il faut encadrer chaque condition par des crochets. Prenons un exemple :
        #!/bin/bash

        if [ $# -ge 1 ] && [ $1 = 'koala' ]
        then
                echo "Bravo !"
                echo "Vous connaissez le mot de passe"
        else
                echo "Vous n'avez pas le bon mot de passe"
        fi

Inverser un test
Il est possible d'inverser un test en utilisant la négation. En bash, celle-ci est exprimée par le point d'exclamation « ! ».
        if [ ! -e fichier ]
        then
                echo "Le fichier n'existe pas"
        fi

case : tester plusieurs conditions à la fois
On a vu tout à l'heure unifun peu complexe qui faisait appel à deselifet à unelse :
Ce genre de « grosifqui teste toujours la même variable » ne pose pas de problème mais n'est pas forcément très facile à lire pour le programmeur. À la place, il est possible d’utiliser l'instructioncasesi nous voulons.
Le rôle de case est de tester la valeur d'une même variable, mais de manière plus concise et lisible.
Voyons comment on écrirait la condition précédente avec un case :
        #!/bin/bash

        case $1 in
                "Bruno")
                        echo "Salut Bruno !"
                        ;;
                "Michel")
                        echo "Bien le bonjour Michel"
                        ;;
                "Jean")
                        echo "Hé Jean, ça va ?"
                        ;;
                *)
                        echo "J'te connais pas, ouste !"
                        ;;
        esac
Nous pouvons aussi faire des « ou » dans uncase. Dans ce cas, petit piège, il ne faut pas mettre deux||mais un seul ! Exemple :

        #!/bin/bash

        case $1 in
                "Chien" | "Chat" | "Souris")
                        echo "C'est un mammifère"
                        ;;
                "Moineau" | "Pigeon")
                        echo "C'est un oiseau"
                        ;;
                *)
                        echo "Je ne sais pas ce que c'est"
                        ;;
        esac

En résumé

    On effectue des tests dans ses programmes grâce aux  if,  then,  [[ elif, then, fi] else,] fi.

    On peut comparer deux chaînes de caractères entre elles, mais aussi des nombres. On peut également effectuer des tests sur des fichiers : est-ce que celui-ci exis‌te ? Est-il exécutable ? Etc.

    Au besoin, il est possible de combiner plusieurs tests à la fois avec les symboles&&(ET) et||(OU).

    Le symbole!(point d'exclamation) exprime la négation dans une condition.

    Lorsque l'on effectue beaucoup de tests sur une même variable, il est parfois plus pratique d'utiliser un bloccase in… esacplutôt qu'un blocif… fi.

while : boucler « tant que »

    TANT QUE test
    FAIRE
    ------> effectuer_une_action
    RECOMMENCER    +

    while [ test ]
    do
            echo 'Action en boucle'
    done

exemple :

    #!/bin/bash

    while [ -z $reponse ] || [ $reponse != 'oui' ]
    do
            read -p 'Dites oui : ' reponse
    done

Il existe aussi le mot cléuntil, qui est l'exact inverse dewhile. Il signifie « Jusqu'à ce que ».
Remplacez justewhileparuntildans le code précédent pour l'essayer.

for : boucler sur une liste de valeurs
    POUR variable PRENANT valeur1 valeur2 valeur3
    FAIRE
    ------> effectuer_une_action
    VALEUR_SUIVANTE

    #!/bin/bash

    for variable in 'valeur1' 'valeur2' 'valeur3'
    do
            echo "La variable vaut $variable"
    done

    exemple
    #!/bin/bash

    liste_fichiers=`ls`

    for fichier in $liste_fichiers
    do
            echo "Fichier trouvé : $fichier"
    done

    Fichier trouvé : boucles.sh
    Fichier trouvé : conditions.sh
    Fichier trouvé : variables.sh
On pourrait faire un code plus court sans passer par une variable$liste_fichiersen écrivant :

    #!/bin/bash
    for fichier in `ls`
    do
            echo "Fichier trouvé : $fichier"
    done

    #!/bin/bash

    for fichier in `ls`
    do
            mv $fichier $fichier-old
    done

    $ ls
    boucles.sh  conditions.sh  variables.sh
    $ ./boucles.sh
    $ ls
    boucles.sh-old  conditions.sh-old  variables.sh-old

    Unforplus classique

Pour les habitués d'autres langages de programmation, leforest une boucle qui permet de faire prendre à une variable une suite de nombres.

En bash, comme on l'a vu, leforpermet de parcourir une liste de valeurs. Toutefois, en trichant un peu à l'aide de la commandeseq, il est possible de simuler unforclassique :

#!/bin/bash
for i in `seq 1 10`;
do
        echo $i
done

En résumé

    Pour exécuter une série de commandes plusieurs fois, on utilise des boucles.

    whilepermet de boucler tant qu'une condition est remplie. Le fonctionnement des conditions dans les boucles est le même que celui des blocsifdécouverts dans le chapitre précédent.

    forpermet de boucler sur une série de valeurs définies. À l'intérieur de la boucle, une variable prend successivement les valeurs indiquées.