# Généralités du projet

## Fonctionnalités implémentées

### Front

* Fonctionnalités utilisateur non connecté
    * Obtenir une prédiction en entrant le texte d'une offre

* Fonctionnalités utilisateur connecté
    * Consulter ses anciennes prédictions réalisées

* Fonctionnalités administrateur
    * Consulter la liste des formations présentes dans la base de données, possibilité de les modifier et de les supprimer
    * Consulter la liste des offres présentes dans la base de données, possibilité de les modifier et de les supprimer
    * Possibilité de trier les offres 

### Back 

* API fonctionnelle (cf document des routes)
* Possibilité de lancer l'apprentissage au démarrage du serveur
* Possibilité de remplir automatiquement la base de données au démarrage du serveur

### Deeplearning
* Mise en place de l'algorithme de deeplearning de word2Vector
* Mise en place de l'algorithme de deeplearning CNN pour générer le modèle de prediction
* Possibilité d'évaluer une offre en fonction d'un modèle de prédiction 

## Fonctionnalités intéressantes à mettre en place

* Une page pour permetre à l'administrateur d'ajouter des utilisateurs
* Transformer l'algorithme de prédiction CNN pour prédire des équipes et non une filère
* Extraire les pop-ups d'inscription et de connexion du component header
* Validation du compte par email
* Page mot de passe oublié

## Installation du Back-end

* Installer mysql-server et le lancer (pour le choix du nom d'utilisateur et du mot de passe il faut que ça corresponde avec le fichier SmartRecruiting_BackEnd/data/database.py
* Pas besoin de créer les tables, elles seront crées automatiquement en lançant l'application
* Installer Python 3 et pip
* Installer les packages nécessaires : pip install -r requirements.txt

### Ajout des données

* Pour l'initialisation il faut ajouter 3 fichiers dans le dossier data :
  * offers.csv
  * fields.csv
  * contacts.csv
* Les fichiers doivent être encodés en UTF-8 et les champs doivent être séparés par des virgules
* Les différents champs des fichiers sont :
  * offers.csv : Formation,Offre initiale
  * fields.csv : name,description,website
  * contacts.csv : name,surname,role,email,phone,field
* La première ligne des fichiers doit comporter le nom des champs

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
   * Pour lancer le serveur : python runserver.py
   * Paramètres à ajouter :
     * -i, --init : initialiser le modèle et la base de données
     * -r, --reinit : réinitialiser le modèle à partir de la base de données

## Déploiement

### Front

1. Changer l'url de l'api dans src/app/shared/constants.ts
2. Build
```
     ng build
```
3. l'ensemble du site web se situe dans le dossier dist généré par la commande précédente. Il vous suffit donc de copier le contenu du dossier dist dans le dossier public de votre serveur.

### Back

1. Changer les identifiants dans le dossier SmartRecruiting_BackEnd/data/database.py
2. (Optionnel) Changer le port de lancement du serveur (runserver.py)
3. (Optionnel) Si un modèle a déjà été généré copier le modèle dans le dossier data
4. Lancer le serveur


:::danger
Wifi campus n'autorise que le port 80 et 8080. Ainsi si le back tourne sur le port 5555 il est inacessible depuis ce réseau et l'application ne fonctionne pas.

Solution 1 : lancer le front et le back sur deux machines différentes

:::
