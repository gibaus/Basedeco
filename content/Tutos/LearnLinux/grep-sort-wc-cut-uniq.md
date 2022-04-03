grep : filtrer des donn�es

	-i : ne pas tenir compte de la casse (majuscules / minuscules)
	-n : conna�tre les num�ros des lignes
	-v : inverser la recherche : ignorer un mot
	-r : rechercher dans tous les fichiers et sous-dossiers
	-E : expression r�guli�re

� noter qu'il existe aussi la commande rgrep qui est �quivalente � grep -r

Caract�re sp�cial 	Signification

.			Caract�re quelconque			
^			D�but de ligne
$			Fin de ligne
[]			Un des caract�res entre les crochets
?			L'�l�ment pr�c�dent est optionnel (peut �tre pr�sent 0 ou 1 fois)
*			L'�l�ment pr�c�dent peut �tre pr�sent 0, 1 ou plusieurs fois
+			L'�l�ment pr�c�dent doit �tre pr�sent 1 ou plusieurs fois
|			Ou
()			Groupement d'expressions

Tout d'abord, il faut savoir qu'on doit utiliser l'option -E pour faire comprendre � grep que l'on utilise une expression r�guli�re.

sort : trier les lignes
	-o : �crire le r�sultat dans un fichier
	-r : trier en ordre inverse
	-R : trier al�atoirement
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
	-m : compter le nombre de caract�res

uniq : supprimer les doublons
	-c : compter le nombre d'occurrences
	-d : afficher uniquement les lignes pr�sentes en double

cut : couper une partie du fichier
	-d : indique quel est le d�limiteur dans le fichier
	-f : indique le num�ro du ou des champs � couper

En r�sum�

    grep est une commande couramment utilis�e pour rechercher un mot dans un fichier.

    On peut utiliser des expressions r�guli�res, un syst�me complexe mais puissant, pour effectuer des recherches pr�cises. On fait dans ce cas appel � la commande egrep.

    sort trie des lignes de texte par ordre alphab�tique. Le param�tre -n permet de trier par ordre num�rique.

    wc compte le nombre de lignes, de mots et d'octets dans un fichier.

    uniq supprime les doublons d'un fichier.

    cut coupe une partie d'un fichier.

> : rediriger dans un nouveau fichier
>> : rediriger � la fin d'un fichier
2>, 2>> et 2>&1 : rediriger les erreurs
cut -d , -f 1 fichier_inexistant.csv > eleves.txt 2> erreurs.log
< et << : lire depuis un fichier ou le clavier
| : cha�ner les commandes
$ cut -d , -f 1 notes.csv | sort