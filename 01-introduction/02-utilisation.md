# Utilisation de Webpack

* En ligne de commande (installation globale) :

```
webpack <entree.js> <resultat.js>
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