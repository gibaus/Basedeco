grep : filtrer des données

	-i : ne pas tenir compte de la casse (majuscules / minuscules)
	-n : connaître les numéros des lignes
	-v : inverser la recherche : ignorer un mot
	-r : rechercher dans tous les fichiers et sous-dossiers
	-E : expression régulière

À noter qu'il existe aussi la commande rgrep qui est équivalente à grep -r

Caractère spécial 	Signification

.			Caractère quelconque			
^			Début de ligne
$			Fin de ligne
[]			Un des caractères entre les crochets
?			L'élément précédent est optionnel (peut être présent 0 ou 1 fois)
*			L'élément précédent peut être présent 0, 1 ou plusieurs fois
+			L'élément précédent doit être présent 1 ou plusieurs fois
|			Ou
()			Groupement d'expressions

Tout d'abord, il faut savoir qu'on doit utiliser l'option -E pour faire comprendre à grep que l'on utilise une expression régulière.

sort : trier les lignes
	-o : écrire le résultat dans un fichier
	-r : trier en ordre inverse
	-R : trier aléatoirement
	-n : trier des nombres

wc : compter le nombre de lignes

$ wc noms.txt 

 8  8 64 noms.txt
Ces trois nombres signifient, dans l'ordre :

    le nombre de lignes.

    le nombre de mots.

    le nombre d'octets.

	-l : compter le nombre de lignes
	-w : compter le nombre de mots
	-c : compter le nombre d'octets
	-m : compter le nombre de caractères

uniq : supprimer les doublons
	-c : compter le nombre d'occurrences
	-d : afficher uniquement les lignes présentes en double

cut : couper une partie du fichier
	-d : indique quel est le délimiteur dans le fichier
	-f : indique le numéro du ou des champs à couper

En résumé

    grep est une commande couramment utilisée pour rechercher un mot dans un fichier.

    On peut utiliser des expressions régulières, un système complexe mais puissant, pour effectuer des recherches précises. On fait dans ce cas appel à la commande egrep.

    sort trie des lignes de texte par ordre alphabétique. Le paramètre -n permet de trier par ordre numérique.

    wc compte le nombre de lignes, de mots et d'octets dans un fichier.

    uniq supprime les doublons d'un fichier.

    cut coupe une partie d'un fichier.

> : rediriger dans un nouveau fichier
>> : rediriger à la fin d'un fichier
2>, 2>> et 2>&1 : rediriger les erreurs
cut -d , -f 1 fichier_inexistant.csv > eleves.txt 2> erreurs.log
< et << : lire depuis un fichier ou le clavier
| : chaîner les commandes
$ cut -d , -f 1 notes.csv | sort