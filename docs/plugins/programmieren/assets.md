### Assets

Im Assets Verzeichnis findet sich die Assets.php und das `images` Verzeichnis. Hier können Sie beliebige Verzeichnisse ergänzen und nutzen.

Die Assets.php sieht folgendermaßen aus, hier das Skelett der Datei.

```php
<?php
namespace Plugins\testplugin\assets;
//use ....

/**
 * Controller für Assets - internal Assets
 * @Route("/testplugin/", name="assets_testplugin_")
 */
class Assets extends AbstractController
{
	/**
	 * @Route("style.css", name="css")
	 * @return Response
	 */
	public function index():Response
	{
		....
	}

	/**
	 * @Route("script.js", name="js")
	 * @return Response
	 */
	public function script():Response
	{
		....
	}

	/**
	 * @Route("image", name="img")
	 * @param Request $request
	 * @return BinaryFileResponse
	 */
	public function showImage(Request $request): BinaryFileResponse
	{
		....
    }
}
?>
```

Wie Sie sehen können werden hier verschiedene Bereiche abgedeckt, es werden CSS, JS und Bilddateien über das Skript jeweils ausgegeben und teilweise auch eigene Termplates verwendet.

Beispiel die Methoden script.js

```php
/**
	 * @Route("script.js", name="js")
	 * @return Response
	 */
	public function script():Response
	{
		$response = new JavascriptResponse();
        
		// Workaround: HTTP-Header Cache-Control würde sonst auf private, must-revalidate etc. gesetzt
		Utils::resetCacheControl($response);
        
		// Lebensdauer der CSS-Datei auf ein Jahr setzen, da ein Zeitstempel an die CSS-Route angehängt wird
		$response->headers->remove('Cache-Control');
        
		$response->setCache([
			'max_age' => 31536000,
			'immutable' => true,
			'public' => true,
		]);
		$parameters = array();
		return $this->render('/'.CONFIG::PLUGIN_DIR_NAME.'/templates/internal/script.js.twig', $parameters, $response);
	}
```

#### Route

Im Kommentar wird die Route festgelegt unter der die Methode aufgerufen werden soll hier script.js. Und es wird festgelegt dass ein Response erfolgen soll.

Zuerst wird mit new JavascriptResponse(); festgelegt dass es sich um eine Javascript Datei handelt. Dann werden mit Hilfe bestimmter Kernfunktionen die CacheControl Header zurückgesetzt damit die Dateien direkt geladen werden können.

Wichtig zu verstehen ist folgender Aufruf

```php
return $this->render('/'.CONFIG::PLUGIN_DIR_NAME.'/templates/internal/script.js.twig', $parameters, $response);
```

#### Hier wird an den Controller folgendes zurückgegeben.

1. Der Name des Templates das verarbeitet werden soll
2. Zusätzliche Parameter die an das Template gegeben werden sollen - es wird TWIG verwendet
3. Der Response wird mit diversen Headern versehen

Vom Prinzip her laufen alle Controller Aufrufe ähnlich ab. 