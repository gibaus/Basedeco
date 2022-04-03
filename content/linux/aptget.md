---
title: "apt-get"
description: "Learn Linux"
date: 2022-04-03T14:42:04+02:00
tags: [Linux]
draft: False
---

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
