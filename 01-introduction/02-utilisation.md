# Utilisation de Webpack

* En ligne de commande (installation globale) :

```
webpack
```

* Depuis un script Node

```js
var webpack = require("webpack");

webpack({
  // configuration
}, function(err, stats) {
  // ...
});
```

Structure de projet par défaut Webpack :

```
/dist
    index.html
    main.js (fichier généré par Webpack)
/src
    index.js
    autreModule1.js
    autreModule2.js
    /autreModule3
        autreModule31.js
```