# Plugins

_Webpack_ offre une API de définition de plugin permettant d'étendre son fonctionnement.

La liste des plugins est disponible à l'adresse : https://webpack.js.org/plugins/.

Exemple de plugins :
* **HtmlWebpackPlugin** : génère un fichier HTML chargeant les modules gérés par _Webpack_.
* **UglifyjsWebpackPlugin** : minifier les ressources JavaScript.

---
# Plugins

Exemple de configuration :

```
npm i --save-dev uglifyjs-webpack-plugin
```
```js
var UglifyJSPlugin = require('uglifyjs-webpack-plugin');

module.exports = {
    entry: {... },
    output: {...},
    plugins: [
        new UglifyJSPlugin()
    ]
};
```