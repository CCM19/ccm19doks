# Einleitung - Plugins selber Programmieren

Diese Anleitung richtet sich an alle die Plugins selber erstellen möchten. Zum derzeitigen Zeitpunkt können die Plugins noch nicht über eine Infrastruktur bereit gestellt werden, sondern sie müssen durch unser Team freigegeben und auch ins System integriert werden. Bei der Beschreibung hier gehen wir davon aus dass Sie mehr als nur Grundkenntnisse in PHP, HTML, CSS, und Javascript besitzen sowie das PHP Framework Symfony kennen.



## Verzeichnisstruktur eines Plugins

Die Verzeichnisse sind generell folgendermaßen aufgebaut, natürlich können Sie davon in einem gewissen Rahmen abweichen indem Sie z.B. noch Unterverzeichnisse in `templates` oder `src` ergänzen.

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
    ├── src
    │   ├── controller
    │   │   └── TestPlugin.php
    │   └── model
    │       └── TestPluginModell.php
    ├── templates
    │   ├── index.html.twig
    │   ├── index.html.twig
    │   ├── list.html.twig
    │   ├── script.js.twig
    │   └── style-css.css.twig
    ├── translations
    │   ├── messages.de.twig
    │   └── messages.xx.twig
    └── vendor

```

Sie sehen hier den Aufbau des Testplugins. So sollten Sie also auch Ihr Testplugin aufbauen.

## Testplugin

Das Testplugin ist derzeit auch auf github zu finden im folgenden Repository: .... (noch offen)

## Einbindung

Eingebunden wird das Plugin folgendermaßen. Es gibt im Verzeichnis `var`  die json Datei `cm-plugins.json` diese hat z.B. folgenden Inhalt.

```json
{
  "f5c45c8": {
	"pluginUID": "jpdubuehl35gozfvkshjbdf",
	"name": "Erweiterte Statistik",
	"description": "Dieses Plugin stellt eine erweiterte Statistik zur Verf\u00fcgung ",
	"menupunktname": "Statistik \/ Analyse",
	"menuitemroute": "app_testplugin_index",
	"faIcon": "fa-bar-chart-o",
	"version": "1.1",
	"versionID": "knp0728zifgzzgaitgjdkvh",
	"free": true,
	"price": "0,00 EUR",
	"img": "data:image\/png;base64, base64ImagesString",
	"dirname": "statistics\/",
	"activateForAllAccounts": "on",
	"activateForAllAccountsOnTheirOwn": null
  }
}
```



**"f5c45c8"**

Key - sollte einzigartig sein :-)

**pluginUID**

(string) Ein frei wählbarer 23 Stellen langer String der eindeutig ist.

**name**

(string) Der Name Ihres Plugins

**description**

(string) Beschreibung Ihres Plugins

**menupunktname**

(string) Der Name des Menüpunktes zum Plugin in der Administration

**menuitemroute**

(string) //klein_unterstriche - die Route zum Plugin - diese sollte dann auch in Ihrem Plugin so zu finden sein.

```php
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
	{
```

**faIcon**

(string) Ein FontAwesome Favivon auf Grundlage der enthaltenen - da bitte im Verzeichnis `public` reinschauen bzw einen Editor nutzen der die Einbindung auflösen kann - was z.B. mit PHPStorm super funktioniert.

**version**

(string) - naja - die Versiosnr ebend...

**versionID**

(string) eine eindeutige VersionsID - wird derzeit nicht genutzt - könnte aber in Zukunft so kommen

**free**

(bool) - true oder false - also kostenlos oder nicht.

**price**

(string) Falls nicht free - dann den Preis hier eintragen

**img**

(string) - base64 kodiertes Bild für die Vorschau - am besten klein rechnen und die Größe anpassen.

**dirname**

(string) - der Name des Verzeichnisses wo das Plugin lokalisiert wird unterhalb von `plugins`

**activateForAllAccounts**

(string) - on oder off oder null- wird dynamisch befüllt über die Administration - kann aber vorausgefüllt werden. Beschreibt ob das Plugin direkt für alle Nutzer aktiv ist. 

**activateForAllAccountsOnTheirOwn**

(string) - on oder off oder null - wird dynamisch befüllt über die Administration - kann aber vorausgefüllt werden. Beschreibt ob jeder Account Owner das Plugin für sich aktivieren muss.

## Aktivierung

Liegt das Plugin nun in dieser Form vor und ist die json Datei aktuell dann kann man das Plugin aktivieren und es sollte direkt zur Verfügung stehen sobald man die Administration aufruft. Für das Testplugin sieht das dann so aus:





