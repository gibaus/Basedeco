---
title: "Commandes"
description: "Learn Linux"
date: 2021-05-29T07:17:10Z
tags: [Linux]
draft: False
---

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
