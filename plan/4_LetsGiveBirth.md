#LetsGiveBirth

## Le status
Pour savoir ce qui est modifié dans votre dépôt local, utilisez la commande :
```sh
git status
```
Dans le résultat, vous trouverez :
- la branche sur laquelle vous vous trouvez
- l'état de votre dépôt local par rapport au dépôt distant (seulement dans le sens de la montée par défaut)
- les changements en attente de commit
- les changements pas encore suivis

Si vous souhaitez connaitre la position de votre dépôt local par rapport au dépôt distant, vous pouvez mettre à jour préalablement l'index :
```sh
git remote update && git status
```

## Le suivi de colis
Quand un ou plusieurs de vos fichiers ne fait pas partie du tracking et que vous souhaitez l'ajouter au dépôt local (pour ensuite l'envoyer vers le dépôt distant) :
- Pour ajouter un seul fichier :
```sh
git add <fichier>
```
- Pour ajouter plusieurs fichiers :
```sh
git add <fichier> [<fichier>...]
```
- Pour ajouter tous les fichiers :
```sh
git add .
```

## Le postage
La commande ```commit``` vous permet d'envoyer une ou plusieurs modifications vers le dépôt local.
- Pour un fichier :
```sh
git commit -m "<message>" <fichier>
```
- Pour plusieurs fichiers :
```sh
git commit -m "<message>" <fichier> [<fichier>...]
```
- Pour tous les fichiers :
  - Solution en une seule action :
  ```sh
  git commit -a -m "<message>"
  ```
  - Solution avec éditeur de message :
  ```sh
  git commit -a
  ```
  Ce mode interactif ouvrira un éditeur sur un fichier temporaire qui contiendra le message de commit, le commit sera effectué à la sauvegarde/fermeture si le message édité n'est pas vide.

## La fourgonette du facteur
Vous dépôt local est à jour, mais pour l'instant vous êtes le.a seul.e à pouvoir profiter de votre code. Pour le rendre disponible à "tout le monde" il faut envoyer votre commit sur le dépôt distant :
```sh
git push
```
Cette commande va tout simplement aller déposer les nouveaux commits présent dans votre dépôt local dans le dépôt distant.

## Quand le facteur vient pour vous
Vous n'êtes probablement pas le seul à effectuer des modifications sur le dépôt distant, et viendra un moment où vous voudrez récupérer ce qu'on fait les autres, la commande est simple (en théorie... mais nous y reviendrons) :
```sh
git pull
```
  Cette commande va chercher dans le dépôt distant tous les commits qui ne sont pas encore présent dans votre dépôt local et les rapatrier. C'est le miroir du ```pull```.
