# Loaders

_Webpack_, par défaut, ne sait interpréter comme module uniquement du code JavaScript.

Pour que d'autres types de ressources (CSS, HTML, ...) puissent être utilisés comme module, il faut configurer des _loaders_ dédiés.

La configuration **module.rules** précise les _loaders_ pris en charge.

```js
module.exports = {
  ...
  module: {
    rules: [ ... ]
  }
}
```


Exemple avec `css-loader` (à installer via `npm install --save-dev css-loader`).

```js
module.exports = {
  ...
  module: {
    rules: [
    	{ test: /\.css$/, use: 'css-loader'}
    ]
  }
}
```
```js
// Il devient alors possible de charger des fichiers CSS
require("./mon.fichier.css");
```

Configurer plusieurs _loaders_.

```
npm install --save-dev css-loader
npm install --save-dev ts-loader
```

```js
module.exports = {
  ...
  module: {
    rules: [
    	{ test: /\.css$/, use: 'css-loader'},
        { test: /\.ts$/, use: 'ts-loader' }
    ]
  }
}
```