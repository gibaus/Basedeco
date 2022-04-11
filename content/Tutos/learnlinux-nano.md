nano : editeur de texte 

    Ctrl + G : afficher l'aide ;

    Ctrl + K : couper la ligne de texte (et la mettre dans le presse-papier) ;

    Ctrl + U : coller la ligne de texte que vous venez de couper ;

    Ctrl + C : afficher à quel endroit du fichier votre curseur est positionné (numéro de ligne…) ;

    Ctrl + W : rechercher dans le fichier ;

    Ctrl + O : enregistrer le fichier (écrire) ;

    Ctrl + X : quitter Nano.

	-m : autorise l'utilisation de la souris sous Nano. En console, oui, oui. Vous pouvez vous en servir pour cliquer avec votre souris sur la zone de texte où vous voulez placer votre curseur.

    	-i : indentation automatique. L'alinéa (tabulations) de la ligne précédente sera respecté lorsque vous irez à la ligne. Très utile lorsque vous éditez un fichier de code source.

    	-A : active le retour intelligent au début de la ligne. Normalement, lorsque vous appuyez sur la toucheOrigine(aussi connue sous le nom deHome) située à côté de la toucheFin, le curseur se repositionne au tout début de la ligne. Avec cette commande, il se positionnera après les alinéas. Comme-i, il s'agit d'une option utile avant tout pour les programmeurs.


Configurer Nano avec .nanorc

set mouse
set autoindent
set smarthome