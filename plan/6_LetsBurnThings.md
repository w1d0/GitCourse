# LetsBurnThings

## Le brouillard
Parfois après 2 heures à tatonner, vous allez vouloir brûler votre espace de travil pour repartir d'une base saine, si vous n'avez pas de stash, pas de commit non poussé, vous pouvez toujours utiliser la méthode du rage quit, mais si vous ne voulez pas complètement tout perdre, vous pouvez utiliser :
```sh
git add .
git reset HEAD --hard
```
Pour faire court, vous ajoutez tout à votre dépôt local puis supprimez tout pour revenir à l'état de votre dernier commit.

## Le doute
Vous venez de commiter, mais un doute vous vient, et vous voulez annuler votre commit :
```sh
git reset --soft HEAD~1
```

## Le napalm
Pour supprimer tous les commits locaux, et revenir à l'état du dépôt distant :
```sh
git reset --hard <remote>/<branch>
```
