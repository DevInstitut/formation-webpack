# Output

La propriété **output** définit le ou les fichier(s) de sortie de _Webpack_.

```js
var path = require('path');

module.exports = {
  entry: './src/app.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'app.bundle.js'
  }
}
```
Dans ce cas, le fichier généré sera `./dist/app.bundle.js`.