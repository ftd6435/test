# test

PETIT RAPPEL SUR LES LIGNE DE COMMANDE DE BASE

        ECRIRE DANS UN FIC : ex : echo "texte a ajouter" >> nomFichier.txt
        LIRE LE FIC : cat nomFichier.txt
        REPERTOIRE COURANT : pwd

====> POUR CONFIGURER GIT DE FACON GLOBALE

        ex : git --global user.email "pk8diallo@gmail.com"
            git --global user.name "pathepk"

====> AU CAS OU YA UNE ERREUR DONC ON VEUT MODIFIER

            ex : git --global --replace-all user.name || user.email "valeur"
        Et si vous vous voulez ajouter un username ou email
            git --global --add user.name || user.email "valeur"

===> VERIFIER LA CONFIGURATION GLOBALE

        ex : git config --global --list || git config --list

====> POUR DESINDEXCER UN FICHIER ON UTILISE LA COMMANDE SUIVANTE

        ex : git reset index.html

====> POUR AFFICHER LA MODIFICATION DES FICHIER INDEXER ET LES FICHIER DEJA COMMITER

        ex : git diff --cached

====> POUR AFFICHER LA DIFFERENCE ENTRE LES FICHIER INDEXER OU COMMITER AVEC LES FICHIER NON INDEXER

        ex : git diff (ici sans paramètre)

====> POUR AFFICHER LES COMMITE

        ex : git log || git log -n (nombre de commit q'on desire afficher)

====> POUR VOYAGER DANS L'HISTORIQUE DES COMMITES

            ex : git checkout (id du sh)
        pour revenir sur la branche principal master
            git checkout master

====> POUR EVITER DES TAG A LA PLACE DES SH IL FAUT NOMMER LES COMMITES

    on deplace d'abord sur le commit qu'on veux nommer avec la commande git checkout
    puis on nomme maintenant comme suit :
        ex : git tag (le nom) || git tag version1

    POUR SUPPRIMER LE NOM
        git tag --delete (nom)

    POUR PUSH LES TAGS SUR LE DEPOT DISTANT

        EX : git push --tags

====> POUR RECUPERER LES MODIFICATION EFFECTUER SUR LE DEPOT DISTANT

    ex : git fetch
    APRES RECUPERATION ON ACTUALISE SUR LE DEPOT LOCAL AVEC LA COMMANDE SUIVANTE
        git pull
    L'option --rebase (permet de gerer les conflits automatiquement lors du pull du remote)
        git pull --rebase

+++++++ TRAVAIL EN EQUIPE +++++++++++++

====> POUR VERIFIER LES MODIFICATION AVEC PLUS DE PRECISION SUR L'AUTHEUR AU NIVEAU DE CHAQUE LIGNE DE CODE

               EX : git blame nomFichier.html || .css || .js etc...

                POUR REDUIRE LE NOMBRE DE LIGNE OU PRECISER
                        git blame -L 10,20 nomFichier.html (A partir de la ligne 10 a la ligne 20)

====> POUR SWITCHER SUR UN AUTRE CHECKOUT SANS ENREGISTRER LES MODIFICATION COURANTE SUR LA BRANCHE HEAD
ON UTILISE LES STASH :

      ex : git stash save "message pour le stash"

      Pour voir la liste des stash
        git stash list
      Pour voir le contenu de ce stash
        git stash show numeroStash
      Qaund on revient sur la branche master, pour la reaffecter sa stash de MODIFICATION
        git stash pop numeroStash

====> NOTION DE BRANCHE

        Pour créée une branche
            git branch nomBranch
        Pour switcher sur la branche
            git checkout nomBranch
        Après modification [add, commit] pour pusher sur le depot distant
        On essaie de créée la branche sur le remote et pusher en meme temps a la commande suivante
            git push --set-upstream origin nomBranch
        Pour lister les branche local et celle du remote
            git branch || git branch -a
        Pour copier un commit sur une branche
            git cherry-pick nomShawan (ou ID)
