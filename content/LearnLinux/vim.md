vim

i : insérer du texte
h, j, k, l : se déplacer dans tous les sens
0 et $ : se déplacer en début et fin de ligne
w : se déplacer de mot en mot
:w : enregistrer le fichier
:q : quitter
:wq : enregistrer puis quitter
x : effacer des lettres
d : effacer des mots, des lignes…
dd : supprimer une ligne
dw : supprimer un mot
d0 et d$ : supprimer le début ou la fin de la ligne
yy : copier une ligne en mémoire
p : coller
r : remplacer une lettre
u : annuler les modifications
G : sauter à la ligne n° X
/ : rechercher un mot
:s : rechercher et remplacer du texte
:r : fusion de fichiers
:sp : découper l'écran horizontalement
:vsp : découper l'écran verticalement

    Ctrl + w puis Ctrl + w : navigue de viewport en viewport. Répétez l'opération plusieurs fois pour accéder au viewport désiré.
    Ctrl + w puis j : déplace le curseur pour aller au viewport juste en dessous. La même chose fonctionne avec les touches h, k et l que l'on utilise traditionnellement pour se déplacer dans Vim.
    Ctrl + w puis + : agrandit le viewport actuel.
    Ctrl + w puis - : réduit le viewport actuel.
    Ctrl + w puis = : égalise à nouveau la taille des viewports.
    Ctrl + w puis r : échange la position des viewports. Fonctionne aussi avec « R » majuscule pour échanger en sens inverse.
    Ctrl + w puis q : ferme le viewport actuel.

    :! : lancer une commande externe

    :set option
    :set nooption
    :set option=valeur
    :set option?

    cp /etc/vim/vimrc  ~/.vimrc
    vim .vimrc

    syntax : activer la coloration syntaxique

    syntax on
    background : coloration sur un fond sombre
    set background=dark
    set number
    showcmd : afficher la commande en cours
    set showcmd
    ignorecase : ignorer la casse lors de la recherche
    set ignorecase
    mouse : activer le support de la souris
    set mouse=a