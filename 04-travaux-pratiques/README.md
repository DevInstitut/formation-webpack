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

* Visualiser le répertoire _node_modules/.bin_.

* Exécuter Webpack

```
node_modules/.bin/webpack

No configuration file found and no output filename configured via CLI option.
A configuration file could be named 'webpack.config.js' in the current directory.
Use --help to display the CLI options.
```

* Créer les fichiers _app/index.js_ et _app/serviceA.js_.

```
/premiers-pas-webpack
    /app
        index.js
        serviceA.js
```

* Compléter les fichiers :

```js
module.exports.afficher = function() {
    console.log("Service A");
};
```


```js
var serviceA = require("./serviceA");

console.log("bonjour webpack !");

serviceA.afficher();
```

* Exécuter la commande :

```
node_modules/.bin/webpack app/index.js build/bundle.js
```

* Observer le contenu du fichier _build/bundle.js_.

* Créer un fichier _webpack.config.js_

```js
module.exports = {
    // définition des points d'entrée
    // il est possible de définir plusieurs points d'entrée
    entry: './app/index.js',

    output: {
        path: "build",
        filename: "bundle.js"
    }
}
```

* Exécuter la commande :

```
node_modules/.bin/webpack
```

* Compléter le fichier _package.json_

```js
...
"scripts": {
    ...
    "build" : "webpack",
    ...
},
...
```

* Exécuter la commande :

```
npm run build
```

## Plugin

### UglifyjsWebpackPlugin

Nous allons à présent _minifier_ le fichier généré à l'aide du plugin _UglifyjsWebpackPlugin_.


* Installer le plugin

```
npm i --save-dev uglifyjs-webpack-plugin
```

* Configurer le plugin

```js
...
var UglifyJSPlugin = require('uglifyjs-webpack-plugin'); <1>

module.exports = {
    entry: { ...},
    output: { ...},
    plugins: [
        new UglifyJSPlugin() <2>
    ]
};
```

* Exécuter la commande :

```
npm run build
```

* Observer le fichier _./build/bundle.js_.

### HtmlWebpackPlugin

* Installer le plugin :

```
npm install html-webpack-plugin --save-dev
```

* Configurer le plugin

```js
...
var HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    entry: {...},

    output: {...},
    plugins: [
       ...,
        new HtmlWebpackPlugin()
    ]
};
```

* Exécuter la commande :

```
npm run build
```

* Observer le fichier _./build/index.html_.

## Webpack Dev Server

* Installer le serveur Webpack :

```
npm install webpack-dev-server --save-dev
```

* Ajouter une tâche NPM _server_ :


```js
...
"scripts" : {
    ...
    "serve": "webpack-dev-server",
    ...
}
```

* Tester le serveur Web avec _npm run serve_. Vérifier le rechargement à chaud de vos modifications.