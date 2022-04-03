---
title: "Linux Cheat Sheet"
description: LearnLinux"
date: 2021-06-13
tags: [Markdown, Linux]
draft: False
---

### apt-get

gestion des depots :

sudo nano /etc/apt/sources.list

    deb : pour telecharger la version compilee (binaire) des programmes.

C'est ce que vous voudrez faire dans la plupart des cas car c'est la version e prete e l'emploi e ;

    deb-src : permet de recuperer le code source du programme.

Generalement, vous n'en avez pas besoin, sauf si vous etes curieux et que vous voulez voir la source d'un programme.
C'est l'avantage des logiciels libres de pouvoir consulter la source des programmes !

    apt-get
    aptitude


    apt-get update (optionnel) : pour mettre notre cache e jour si ce n'est pas deje fait ;

    	apt-cache search monpaquet (optionnel) : pour rechercher le paquet que nous voulons telecharger si nous ne connaissons pas son nom exact ;

    	apt-get install monpaquet : pour telecharger et installer notre paquet.

apt-get update : mettre e jour le cache des paquets
apt-cache search : rechercher un paquet
apt-get install : installer un paquet
apt-get autoremove : supprimer un paquet
apt-get upgrade : mettre e jour tous les paquets

### .bashrc

Configurer sa console avec .bashrc

Créer des alias

# enable color support of ls and also add handy aliases

if [ "$TERM" != "dumb" ]; then
eval "`dircolors -b`"
alias ls='ls --color=auto'
#alias dir='ls --color=auto --format=vertical'
#alias vdir='ls --color=auto --format=long'
fi

# some more ls aliases

#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'

alias ls='ls --color=auto'

### Commandes

pwd : afficher le dossier actuel

mateo21@mateo21-desktop:~$ pwd
/home/mateo21

which : connaétre l'emplacement d'une commande

mateo21@mateo21-desktop:~$ which pwd
/bin/pwd

ls : lister les fichiers et dossiers

mateo21@mateo21-desktop:~$ ls
Desktop Examples images log tutos

    -a : afficher tous les fichiers et dossiers cachés
    -F : indique le type d'élément
    -l : liste détaillée
    -h : afficher la taille en Ko, Mo, Goé
    -t : trier par date de derniére modification

cd: changer de dossier
du: taille occupée par les dossiers
cat & less : afficher un fichier

    cat : afficher tout le fichier
    less : afficher le fichier page par page

head & tail : afficher le début et la fin d'un fichier

    head : afficher le début du fichier
    tail : afficher la fin du fichier

touch & mkdir : créer des fichiers et dossiers

    touch : créer un fichier
    mkdir : créer un dossier

cp & mv : copier et déplacer un fichier

    cp : copier un fichier

    -R(un é R é majuscule !), vous pouvez copier un dossier,
    ainsi que tous les sous-dossiers et fichiers qu'il contient !

    mv : déplacer un fichier

rm : supprimer des fichiers et dossiers

    rm : supprimer un fichier

    -i : demander confirmation
    -f : forcer la suppression, quoi qu'il arrive
    -v : dis-moi ce que tu fais, petit cachotier
    -r : supprimer un dossier et son contenu

sudo: exécuter une commande en root

    sudo su : devenir root et le rester

adduser : gestion des utilisateurs
passwd : changer le mot de passe
deluser : supprimer un compte
addgroup : gestion des groupes
usermod : modifier un utilisateur

        -l : renomme l'utilisateur (le nom de son répertoire personnel ne sera pas changé par contre) ;
        -g : change de groupe.

delgroup : supprimer un groupe

chown : : gestion des propriétaires d'un fichier

    d (Directory) : indique si l'élément est un dossier ;

    l (Link) : indique si l'élément est un lien (raccourci) ;

    r (Read) : indique si on peut lire l'élément ;

    w (Write) : indique si on peut modifier l'élément ;

    x (eXecute) : si c'est un fichier, é x é indique qu'on peut l'exécuter.

Ce n'est utile que pour les fichiers exécutables (programmes et scripts).

    Si c'est un dossier, é x é indique qu'on peut le é traverser é,

c'est-é-dire qu'on peut voir les sous-dossiers qu'il contient si on a le droit de lecture dessus.

Attribuer des droits avec des lettres (chmod relatif)

    u = user (propriétaire) ;

    g = group (groupe) ;

    o = other (autres).

é et que :

    + signifie : é Ajouter le droit é ;

    - signifie : é Supprimer le droit é ;

    = signifie : é Affecter le droit é.

-R pour affecter récursivement

locate : une recherche rapide
find : une recherche approfondie

### Compression

tar : assembler des fichiers dans une archive
-cvf : créer une archive tar
-c : signifie créer une archive tar ;
-v : signifie afficher le détail des opérations ;
-f : signifie assembler l'archive dans un fichier.

    -tf : afficher le contenu de l'archive sans l'extraire
    -rvf : ajouter un fichier
    -xvf : extraire les fichiers de l'archive

gzip & bzip2 : compresser une archive

    gzip : c'est le plus connu et le plus utilisé ;
    bzip2 : il est un peu moins fréquemment utilisé. Il compresse mieux mais plus lentement que gzip.

gzip : la compression la plus courante
Pour décompresser l'archive ensuite, il suffit d'utiliser gunzip

bzip2 : la compression la plus puissante
Pour la décompresser, utilisez bunzip2 :

Archiver et compresser en méme temps avec tar
-zcvf : archiver et compresser en gzip
-jcvf : archiver et compresser en bzip2

zcat, zmore & zless : afficher directement un fichier compressé

    zcat : équivalent de cat, capable de lire un fichier compressé (gzippé).
    zmore : équivalent de more, capable de lire un fichier compressé (gzippé).
    zless : équivalent de less, capable de lire un fichier compressé (gzippé).

unzip & unrar : décompresser les .zip et .rar
unzip : décompresser un .zip
unrar : décompresser un .rar

En résumé

    Pour regrouper plusieurs fichiers et dossiers au sein d'un méme fichier (appelé archive), on utilise le programme tar. Celui-ci ne compresse pas les fichiers par défaut, contrairement é zip.
    Il est possible de compresser une archive tar avec le programme gzip (trés couramment utilisé) ou bzip2 (meilleure compression mais plus lente).
    Les archives non compressées ont l'extension .tar, les archives compressées ont l'extension .tar.gz (pour gzip) ou .tar.bz2 (pour bzip2).
    On utilise peu les formats de compression zip et rar sous Linux, mais il est possible de décompresser ces types de fichiers avec les programmes unzip et unrar. Ceux-ci ne sont en général pas installés par défaut.
