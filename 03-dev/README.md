# Webpack en développement

Lors de la phase de développement, _Webpack_ peut de prendre les modifications _à chaud_ via l'option `--watch`.

_Webpack_ fournit le module **webpack-dev-server** (WDS) qui travaille essentiellement en mémoire. Les fichiers temporaires ne sont pas écrits sur le disque mais servis directement par le serveur.

**webpack-dev-server** utilise un module de rechargement à chaud qui fait des mises à jour différentiels.


# Webpack en développement

Pour installer **webpack-dev-server**.

```
npm install webpack-dev-server --save-dev
```

Le script `webpack-dev-server` permet ensuite de démarrer un serveur web avec un rechargement à chaud.