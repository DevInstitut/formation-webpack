# Entry

_Webpack_ crée le graphe de toutes les dépendences de l'application.

Les points d'entrée définissent à _Webpack_ où commencer.

Exemple de point d'entrée :

```js
module.exports = {
  entry: './src/app.js'
}
```
---


Il est possible de définir plusieurs points d'entrée.

```js
module.exports = {
  entry: {
    app: './src/app.js',
    vendors: './src/vendors.js'
  }
}
```