# LetsStart

## Le clone (pas la guerre)
La première commande pour commncer à travailler sous est :
```sh
git clone <repo_distant>
```

Dans notre exemple du jour ce sera donc :
```sh
git clone https://github.com/w1d0/GitTraining.git
```

Qu'est-ce qui se passe derrière cette commande :
- Un dossier portant le nom du repo distant est créé (pour surcharger le nom de ce dossier on peut utiliser une variante de la commande : ```git clone <repo_distant> <nom_du_dossier_local>```)
- Les sources contenues dans la branche ```master``` du repo distant sont téléchargées
- Un dossier ```.git``` est ajouté localement, c'est lui qui contient l'index
- Un lien bidirectionnel est créé entre votre espace de travail et le repo distant.

## Le rage quit
Pour couper tout lien avec un repo Git, il suffit de supprimer le dossier sur votre disque, pour les fans de ligne de commande on lancerait la commande ```rm -rf <repertoire_de_travail>```

Bien entendu cette action est irréversible et tout ce qui n'a pas été transmis au dépôt distant sera perdu.
