# LetsBeMonkeys

## La pousse
Vous pouvez initialiser une branche localement, en utilisant la commande :
```sh
git checkout -b <branche>
```
Cette commande crée la branche et en fait la branche courante.

## La pousse connectée (nettement mieux)
Créez votre branche et pour la connecter lancez :
git push -u origin monkey_branch

## Récolter les fruits
Une fois la fonctionnalité écrite et testée, il est temps de ramener tout ça sur ```master```. Vérifiez que tout est bien committé et poussé.

Passez sur master :
```sh
git checkout master
```
Lancez le merge :
```sh
git merge <branche>
```
Une fois que vous avez vérifié que tout est là :
```sh
git branch -d <branche>
git push origin --delete <branche>
```
