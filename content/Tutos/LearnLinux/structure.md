ossiers.

    bin : contient des programmes (ex�cutables) susceptibles d'�tre utilis�s par tous les utilisateurs de la machine.

    boot : fichiers permettant le d�marrage de Linux.

    dev : fichiers contenant les p�riph�riques. En fait � on en reparlera plus tard � ce dossier contient des sous-dossiers qui � repr�sentent � chacun un p�riph�rique. On y retrouve ainsi par exemple le fichier qui repr�sente le lecteur CD.

    etc : fichiers de configuration.

    home : r�pertoires personnels des utilisateurs. On en a d�j� parl� un peu avant : c'est dans ce dossier que vous placerez vos fichiers personnels, � la mani�re du dossierMes documentsde Windows.

           Chaque utilisateur de l'ordinateur poss�de son dossier personnel. Par exemple, dans mon cas mon dossier personnel se trouve dans/home/mateo21/. S'il y avait un autre utilisateur (appelons-le Patrick) sur mon ordinateur, il aurait eu droit lui aussi � son propre dossier :/home/patrick/.

    lib : dossier contenant les biblioth�ques partag�es (g�n�ralement des fichiers.so) utilis�es par les programmes. C'est en fait l� qu'on trouve l'�quivalent des.dllde Windows.

    media : lorsqu'un p�riph�rique amovible (comme une carte m�moire SD ou une cl� USB) est ins�r� dans votre ordinateur, Linux vous permet d'y acc�der � partir d'un sous-dossier demedia. On parle de montage.

    mnt : c'est un peu pareil quemedia, mais pour un usage plus temporaire.

    opt : r�pertoire utilis� pour les add-ons de programmes.

    proc : contient des informations syst�me.

    root : c'est le dossier personnel de l'utilisateur � root �. Normalement, les dossiers personnels sont plac�s danshome, mais celui de � root � fait exception. En effet, comme je vous l'ai dit dans le chapitre pr�c�dent, � root � est le superutilisateur, le � chef � de la machine en quelque sorte. Il a droit � un espace sp�cial.

    sbin : contient des programmes syst�me importants.

    tmp : dossier temporaire utilis� par les programmes pour stocker des fichiers.

    usr : c'est un des plus gros dossiers, dans lequel vont s'installer la plupart des programmes demand�s par l'utilisateur.

    var : ce dossier contient des donn�es � variables �, souvent des logs (traces �crites de ce qui s'est pass� r�cemment sur l'ordinateur).