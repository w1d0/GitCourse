# LetsLearnHistory

Il est possible de voir l'historique de votre projet (dépôt local et distant), la commande est la suivante :
```sh
git log
```
Cette commande produit le résultat suivant :
```sh
commit c16ce0a8ceaa2be337dbbdadc17641dfc75164c2 (HEAD -> master)
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 07:06:46 2020 +0100

    Marty let's go

commit 9611416d2ccf50cded304e1266a8e1fedce851b6 (origin/master, origin/HEAD)
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 06:46:21 2020 +0100

    Burning things, not man

commit 77128e3d125ad64f0cdb80f7b267a6b2ca38e2b5
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 06:09:23 2020 +0100

    clean up
```
Pour faire simple :
- ```c16ce0a8ceaa2be337dbbdadc17641dfc75164c2``` est un identifiant de commit
- ```(HEAD -> master)``` représente votre dépôt local
- ```(origin/master, origin/HEAD)``` représente votre dépôt distant

Sur ce dépôt, un autre intervenant a fait un commit mais il n'est pas visible, l'index n'en a pas la vue, pour la lui redonner :
```sh
git fetch
```
En relançant un ```log``` on ne voit plus les informations du remote ```origin```, il est donc nécessaire de récupérer la différence avec le remote :
```sh
git rebase <remote>/<branch>
```
Le résultat du log devient le suivant :
```sh
commit 758f2af5b667c5d317f86110d99565ff3ed060fd (HEAD -> master)
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 07:06:46 2020 +0100

    Marty let's go

commit d4af22cdb03f821330e0121b14aab2553161bff6 (origin/master, origin/HEAD)
Merge: 1488a11 9611416
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 07:09:49 2020 +0100

    Merge branch 'master' of https://github.com/w1d0/GitTraining

commit 1488a11691f157b2f43998f344e422d9a638baf3
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 07:09:35 2020 +0100

    changing history

commit 9611416d2ccf50cded304e1266a8e1fedce851b6
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 06:46:21 2020 +0100

    Burning things, not man

commit 77128e3d125ad64f0cdb80f7b267a6b2ca38e2b5
Author: w1d0 <benoit@bearit.fr>
Date:   Wed Feb 5 06:09:23 2020 +0100

    clean up
```
