# Travaux Pratiques

## Premier pas

* Créer un répertoire :

```
/premiers-pas-webpack
```

* Initialiser un projet NPM

```
cd premiers-pas-webpack
npm init -y
```

* Installer Webpack

```
npm install webpack --save-dev
```

* Installer le client Webpack

```
npm install --save-dev webpack-cli
```

* Visualiser le répertoire _node_modules/.bin_.


* Créer les fichiers `dist/index.html`, `src/index.js` et `src/serviceTitre.js`.

```
/premiers-pas-webpack
    /dist
        index.html
    /src
        index.js
        serviceTitre.js
```

* Compléter le fichier `dist/index.html` :

```js
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Démo Webpack</title>

    <script src="main.js"></script>

</head>
<body></body>
</html>
```


* Compléter le fichier `app/serviceTitre.js` :

```js
// insérer titre
export function insererTitre() {
	document.querySelector('body').insertAdjacentHTML('afterbegin', '<h1>Démo Webpack</h1>');
}
```

* Compléter le fichier `src/serviceTitre.js` :

```js
import { insererTitre } from './serviceTitre';


document.addEventListener('DOMContentLoaded', function(event) {
    insererTitre();
});
```

* Exécuter la commande :

```
node_modules/.bin/webpack
```

* Visualiser le contenu du fichier généré `dist/main.js`.

* Observer le contenu du fichier _build/main.js_.

* Afficher la page `dist/index.html` et vérifier l'affichage du titre.

* Compléter le fichier _package.json_

```js
...
"scripts": {
    ...
    "build" : "webpack --mode production",
    ...
},
...
```

* Exécuter la commande :

```
npm run build
```

## Configuration

* Créer un fichier _webpack.config.js_

```js
const path = require('path');

module.exports = {
    entry: './src/index.js',
    output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist')
    }
};
```

Noter que le nom du fichier de sortie est désormais `dist/bundle.js` et non `dist/main.js`.

* Exécuter la commande :

```
npm run build
```

* Vérifier la présence du fichier `dist/bundle.js`.

* Modifier le fichier `index.html` pour qu'il soit cohérent avec notre nouvelle configuration et supprimer le fichier `main.js`.

## Webpack Dev Server

* Installer le serveur Webpack :

```
npm install webpack-dev-server --save-dev
```

* Compléter la configuration Webpack comme suit :

```js
const path = require('path');

module.exports = {
    entry: './src/index.js',
    output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist')
    },
    devServer: {
        contentBase: path.join(__dirname, "dist"),
        compress: true,
        port: 8081
    },
    devtool: "cheap-module-eval-source-map",
    mode : "development"
};
```

* Ajouter une tâche NPM `start` :

```js
...
"scripts" : {
    ...
    "start": "webpack-dev-server",
    ...
}
```

* Tester le serveur Web avec `npm start`.

* Vérifier le rechargement à chaud de vos modifications.

* Vérifier que vous pouvez faire du _debug_ sur vos sources initiales via les outils de développement de votre navigateur.