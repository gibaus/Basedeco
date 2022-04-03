Les fonctions
Qu'est-ce qu'une fonction ?
Une fonction, c’est un ensemble d’instructions, permettant d'effectuer plusieurs tâches avec des paramètres d'entrée différents.
Son utilisation vous permettra de rendre votre programme plus lisible et structuré. Ainsi, il facilitera le développement de votre programme.

    Vous n'êtes pas limité dans le nombre de fonction. Par contre, elles ne doivent pas avoir le même nom.

    Vous pouvez réutiliser les variables globales initialiser dans votre script à l'intérieur ou à l'extérieur de votre fonction.

    Vous pouvez déclarer des variables locales à vos fonctions.

    Une bonne fonction,  c'est une fonction qui traite d'un élément spécifique et récurrent dans votre script.

Comment déclarer une fonction ?
En Bash, il y a deux manières pour déclarer une fonction :

# déclaration méthode 1
        maFonction ()

        {
        bloc d’instructions
        }

        #appel de ma fonction

        maFonction

 ou

# déclaration méthode 2

        function maFonction

        {
        bloc d’instructions
        }

        #appel de la fonction

        maFonction

Vous pourriez par exemple avoir trois fonctions :
    une fonction sauvegarde ;
    une fonction log ;
    une fonction avertissement.

En résumé :

    Une fonction comprend plusieurs instructions.

    Vous pouvez l'appeler autant de fois que vous voulez dans votre code : laissez donc votre fonction assez générique et faites-la varier grâce aux paramètres que vous pouvez préciser en l'appelant.

    Vous pouvez déclarer une fonction Bash avec maFonction ()ou function maFonction.

    Vous faites ensuite appel à votre fonction maFonction() en tapant simplement dans votre code maFonction.