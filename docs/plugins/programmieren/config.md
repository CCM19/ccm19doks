### Config

Der Einstiegspunkt für die Programmierung ist im ersten Schritt die `Config/config.php` - hier werden die wesentlichen Konfigurationen gelegt. Im Testplugin ist der Code noch sehr übersichtlich.

```php
<?php

namespace Plugins\testplugin\Config;

/**
 * Configuration Class for Constants in Class
 * use as "use Plugins\testplugin\Config\Config;"
 */
class Config {

	const PLUGIN_NAME 		= 'Test Plugin';
	const PLUGIN_DIR_NAME 	= 'testplugin';
	const PLUGIN_UUID 		= "mgo8752z4togzughweo587gh";


	public function __construct(){}
}
?>
```

Festgelegt wird der Namenspace - beachten dass der bei allen Dateien immer auch dann in das Plugins Verzeichnis verweist, das muss also manuell definiert werden. Am besten mit Verzeichnisweitem Suchen / Ersetzen umstellen.

Beschrieben ist auch die korrekte Einbindung im Kommentar in anderen Klassen.

### 