# Plugins selber Programmieren

Die Plugins sind generell folgendermaßen aufgebaut

```bash
testplugin
    ├── assets
    │   ├── Assets.php
    │   └── images
    │       └── testimage1.jpg
    ├── composer.json
    ├── Config
    │   └── Config.php
    ├── index.html
    ├── less
    ├── public
    ├── src
    │   ├── controller
    │   │   └── TestPlugin.php
    │   └── model
    │       └── TestPluginModell.php
    ├── templates
    │   ├── index.html.twig
    │   ├── list.html.twig
    │   ├── script.js.twig
    │   └── style-css.css.twig
    ├── translations
    └── vendor

```

Sie sehen hier den Aufbau des Testplugins.

