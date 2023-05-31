---
title: "Compression"
description: "Learn Linux"
date: 2023-05-30T14:42:04+02:00
tags: [Linux]
draft: False
---

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
