# Généralité du projet

## Fonctionnalités implémentées

### Front

* Fonctionnalité utilisateur non connecté
    * Obtenir une prédiction en entrant le texte d'une offre

* Fonctionnalité utilisateur connecté
    * Consulter ses anciennes prédictions réalisées

* Fonctionnalité administrateur
    * Consulter la liste des formations présente dans la base de données, possibilité de les modifier et de les supprimer
    * Consulter la liste des offres présentes dans la base de données, possibilité de les modifier et de les supprimer
    * Possibilité de trier les offres 

### Back 

* API fonctionnelle (cf document des routes)
* Possibilité de lancer l'apprentissage au démarrage du serveur
* Possibilité de remplir automatiquement la base de données au démarrage du serveur

### Deeplearning
* Mise en place de l'algorithme de deeplearning de word2Vector
* Mise en place de l'algorithme de deeplearning CNN pour générer le model de prediction
* Possibilité d'évaluer une offre en fonction d'un model de prédiction 

## Fonctionnalité intéressante à mettre en place

* Une page pour permetre à l'administrateur d'ajouter des utilisateurs
* Transformer l'algorithme de prédiction CNN pour prédire des équipes et non une fillère
* Extraire les pop-ups d'inscription et de connexion du component header
* Validation du compte par eamil
* Page mot de passe oublié

## Installation du Back-end


/*TODO*/

## Installation du Front-end

### Windows

1. Installer Node.js : https://nodejs.org/en/download/
2. cloner le repo git
3. Dans le dossier Front-End lancer la commande suivante
```shell
    npm install
    npm install -g @angular/cli
```


### Linux
1. Installer Node.js 
```shell
    curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
    sudo apt install -y nodejs
```
2. Installer nvm (https://github.com/maximegris/angular-electron)
```
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash

```
3. cloner le repo git
4. Dans le dossier Front-End lancer la commande suivante
```shell
    npm install
    npm install -g @angular/cli
```

## Lancement

* Lancer le front
```shell
     ng serve --open
```

* Lancer la back-end
/*TODO*/

## Déploiement

### Front

1. Changer l'url de l'api dans src/app/shared/constants.ts
2. Build
```
     ng build
```
3. l'ensemble du site web se situe dans le dossier dist généré par la commande précédente. Il vous suffit donc de copier le contenu du dossier dist dans le dossier publique de votre serveur.

### Back

1. Changer les identifiant dans le dossier SmartRecruiting_BackEnd/data/database.py
2. (Optionnel) Changer le port de lancement du serveur(runserver.py)
3. (Optionnel) Si un model a déjà été génré copier le model dans le dossier data
4. Lancer le serveur


:::danger
Wifi campus n'autorise que le port 80 et 8080. Ainis si le back tourne sur le port 5555 il est inacessible depuis ce réseaux et l'application ne fonctionne pas.

Solution 1 : lancer la front et le back sur deux machines différentes

:::
