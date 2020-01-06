# Pouchdb
This is a plugin for TiddlyWiki 5. It just contains the pouchdb library ready to be embedded into tiddlywiki.
It does not provides any functionality by itself and it is meant to be used as a dependency for other plugins.

# Installation

This plugin is published as an npm package, you can install it from there by just doing `npm install tw-pouchdb`.
To use it in tiddlywiki server version add the node_modules path of this package as an env variable when starting tiddlywiki:

```bash
TIDDLYWIKI_PLUGIN_PATH=node_modules/tw-pouchdb tiddlywiki ./wiki --verbose --server 8088 $:/core/save/all text/plain text/html
```

You also need to include the plugin name (which is `danielo515/pouchdb`) on the plugins list of tiddlywiki.info file, which lives under your `./wiki` directory.
Here is an example file

 **./wiki/tiddlywiki.info**
```json
{
  "plugins": [
    "danielo515/pouchdb",
    "danielo515/tiddlypouch"
  ],
  "themes": [
    "tiddlywiki/vanilla",
  ],
  "languages": [
    "en-US"
  ],
  "build": {
    "index": [
      "--rendertiddler", "$:/tiddlypouch/save/deploy", "index.html", "text/plain"
    ],
    "favicon": [
      "--savetiddler", "$:/favicon.ico", "favicon.ico"
    ]
  }
}

```
