# sass-bootstrap-demo

## Etapes pour reproduire le repository

### Installer node

https://nodejs.org/en/download/

### Créer le répertoire du projet

sass-bootstrap-demo
aller dans le répertoire

### Initialiser npm

En ligne de commande:

```bash
npm init
```

### Install Sass via npm

En ligne de commande:

```bash
npm install --save-dev sass
```

### Création des fichiers

index.html
style.scss
ajout d'un link dans le html qui pointe vers le futur fichier css généré

### Création du script dans package.json

```json
"scripts": {
"compile-css": "sass style.scss css/generated-by-sass.css"
},
```

décomposé:

``compile-css`` nom du script

``sass`` nom de l'exécutable du compilateur (la ligne de commande le connait car on a fait le npm install dans le dossier)

``style.scss`` nom du fichier source

``css/generated-by-sass.css`` chemin du fichier de sortie

Tous ces noms sauf ``sass`` sont customisables

### Exécution du script de compilation

```bash
npm run compile-css
```

Le fichier dans ``css`` doit être écrasé par les modifications apportées

### Ouvrir le index.html dans le navigateur


### Install Bootstrap

```bash
npm install --save bootstrap
```

### Importer tout bootstrap

Il est possible d'importer uniquement la partie qu'on veut, mais pour la simplicité, on importe tout.
Ajouter le code suivant en haut du fichier styles.scss

```sass
@import "node_modules/bootstrap/scss/bootstrap";
```

Noter l'absence de ``.scss`` à la fin, ça fait pourtant référence au fichier bootstrap.scss du dossier.

### Utiliser bootstrap

Ajouter un composant html et le décorer avec une classe bootstrap.
On a choisi ici un simple bouton:

```html
<button type="button" class="btn btn-primary">Bouton</button>
```

### Exécution du script de compilation

```bash
npm run compile-css
```

Noter la taille "légèrement" augmentée du fichier css de sortie.

### Ouvrir le index.html dans le navigateur


### Créer un fichier de variables d'override de la lib bootstrap

On l'a appelé ``bootstrap-override-variables.scss`` et placé au même niveau que style.scss

### Importer le fichier d'overrides

Il faut le placer au DESSUS de l'import de bootstrap, comme ceci:

```sass
@import "bootstrap-override-variables";
@import "node_modules/bootstrap/scss/bootstrap";
```

### Override des variables

La doc qui en parle est là: https://getbootstrap.com/docs/5.2/customize/sass/

On va customiser le bouton mis précédemment, à l'aide de la doc du composant button
https://getbootstrap.com/docs/5.2/components/buttons/#sass-variables
et de la doc sur les couleurs
https://getbootstrap.com/docs/5.2/customize/color/

Tous les futurs boutons auront les nouvelles valeurs de propriété par défaut.
