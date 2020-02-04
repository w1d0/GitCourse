# LetsPutTheElfOnTheShelf
Je parlais de magie dans la présentation des "espaces", voilà donc comment utiliser la remise (en partie).

## Dépôt de l'elfe sur l'étagère
Parfois, vous aurez besoin de changer rapidement de contexte, en plein milieu de l'écriture d'une fonctionalité, et si vous n'êtes pas seul sur vôtre branche, vous ne pourrez pas commiter. Sous SVN, vous auriez systématiquement tout perdu pour abandonner ce que vous avez en cours. Sous Git, vous pouvez mettre de côté vos développements en cours, avec la commande :
```sh
git stash save
```
Si on vous dérange dans la nouvelle fonctionalité, avec une troisième par exemple (ou un bug de prod), cette commande est répétable presque à l'infini. Bon courage pour les dépiler si les priorités changent (les astuces arrivent)

## Compter les elfes
Vous attaquez le sixième changement de priorité, vous ne savez plus ou vous en êtes, vous voulez savoir tout ce que vous avez de côté, facile avec la commande :
```sh
git stash list
```
Vous découvrez avec horreur le résultat suivant :
```sh
MacBook-Pro-de-Benoit:GitTraining w1d0$ git stash list
stash@{0}: On master: messaged stash
stash@{1}: WIP on master: 25c0dbe Pull... Bang
stash@{2}: WIP on master: 25c0dbe Pull... Bang
```
Ici, 3 elfes sur l'étagère, deux dont la racine était le commit ```25c0dbe Pull... Bang``` et un dont le commit n'apparait pas mais qui porte un message ```messaged stash```

Cette commande vous montre donc, le nombre de stash, l'indice le plus bas est votre dernier stash et donc évidemment le plus haut votre ancien.

Pour donner un nom à un stash, il suffit de modifier un peu la commande :
```sh
git stash save '<message>'
```

## Récupérer les elfes
La commande standard pour remettre votre satsh dans votre index "de travail" est :
```sh
git stash pop
```
Cette commande dépile le dernier stash (et ainsi de suite).

Cependant parfois les priorités changent et vous devez reprendre le travail d'une autre fonctionalité, vous pouvez donc volontairement (et explicitement) récupérer un autre stash, avec la commande :
```sh
git stash pop <index_du_stash>
```
Alternativement vous pouvez également utiliser :
```sh
git stash apply <index_du_stash>
```
Si vous refaites un ```stash list``` voius remarquerez que cette commande n'a pas supprimé le stash.

Parfois les fonctionalités peuvent être abandonnées et nul besoin dans ce cas de garder un stash dans la remise, vous pouvez le supprimer avec cette commande :
```sh
git stash drop <index_du_stash>
```

## De l'utilité des elfes
Parfois, vous devrez récupérer des travaux du dépôt distant, mais ce n'est pas possible avec un "dirty index" (c'est-à-dire des chose non commitées), Git vous le dira avec un message ressemblant à celui-ci :
```sh
Updating 2328ff0..5f5b77c
error: Your local changes to the following files would be overwritten by merge:
	dirty_dancer.txt
Please commit your changes or stash them before you merge.
Aborting
```
Dans ce cas vous pouvez faire cet enchainement de commandes :
```sh
git stash save
git pull
git stash pop
```
Vous aurez probablement un conflit (nous y reviendrons), mais au moins vous n'aurez pas perdu vos travaux.
