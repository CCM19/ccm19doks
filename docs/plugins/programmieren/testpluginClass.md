# Testplugin Klasse

Die Testplugin Klasse ist der zentrale Controller des Plugins, hierüber laufen alle Aufrufe. Damit das klappt muss der Eintrag in der json Datei der **menuitemroute** enthät in diesem Controller auch auftauchen -> app_testplugin_index - setzt sich zusammen aus dem Namen in der Beschreibung der Klasse und dem Namen aus der Beschreibung der Funktion name="app_testplugin_" + name="index".

Stimmen die Daten nicht überein wird der Menüpunkt nicht angezeigt - daher bei der Erstellung unbedingt darauf achten dass es da klappt.



```php
<?php
    
namespace Plugins\testplugin\src\controller;
//use

/**
 * Controller for Testplugin - domain dependent
 * @Route("/domains/{_domainId}/plugins/testplugin/", name="app_testplugin_")
 */
class TestPlugin extends DomainDependantController
{
	/**
	 * @Route("index", name="index")
	 * @return Response
	 */
	public function index(): Response
	{}
    
	/**
	 * @Route("testplugin_save", name="save"), methods={"HEAD","POST"})
	 * @param Request $request
	 * @return Response
	 */
	public function editSettings(Request $request, TranslatorInterface $translator): Response
    {}

	/**
	 * @return bool
	 */
	private function setCssAndJSForExternal()
	{}

	/**
	 * Most basic creation of an entry...
	 *
	 * @return bool
	 * Create a new entry with senseless data
	 */
	public function createTestPluginEntry(): bool
	{}
}
?>
```

