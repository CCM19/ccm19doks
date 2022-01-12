# CCM19-Plugins

CCM19 kann durch Plugins um diverse Funktionalitäten erweitert werden.

## Namensgebung

Jedes Plugin hat einen eindeutigen Namen, der aus einem Hersteller-Präfix und dem eigentlichen Plugin-Namen besteht. Der Plugin-Name sollte aus englischen Wörtern bestehen.

Hersteller-Präfixe werden in Zukunft zentral vergeben. Falls Sie Plugins selbst entwickeln, achten Sie derzeit bitte auf einen möglichst eindeutigen Namen, damit beim Herstellerpräfix keine Namenskollisionen auftreten.

Für das Plugin-Verzeichnis wird der Name mit dem Hersteller-Präfix in CamelCase-Schreibweise zusammengesetzt.

Als Plugin-ID im `name`-Feld der `composer.json` wird der Name als `hersteller/pluginname` in snake_case geschrieben.

Vom CCM19-Entwicklerteam entwickelte Plugins tragen den Präfix `Ccm19`.

Ein Plugin von CCM19 für "erweiterten Iframe-Support" würde also `ccm19/extended_iframe` bzw. `Ccm19ExtendedIframe` heißen,
ein Plugin des Herstellers "Example Vendor" z.B. `examplevendor/really_special_plugin` bzw. `ExamplevendorReallySpecialPlugin`.

## Grundstruktur

Ein Plugin wird als Ordner im Verzeichnis `plugins` angelegt und enthält folgende Dateien und Ordner:

- `composer.json` – Metadaten über das Plugin
- `preview.`{`png`|`jpeg`|`svg`|`webp`|`gif`} – Vorschaubild
- `src/` – PHP-Quelldateien (Idealerweise in einer Substruktur wie im CCM19-src-Verzeichnis)
- `src/Controller/` – Controller-PHP-Dateien (optional)
- `config/` – Symfony-Config-Dateien (optional)
- `templates/` – Twig-Templates (optional)
- `translations/` – Übersetzungsdateien (optional)

## Composer.json

Die `composer.json` sieht folgendermaßen aus:

```
{
	"name": "examplevendor/really_special_plugin",
	"description": "This plugin does something really special that should be described here.",
	"version": "1.0",
	"type": "ccm19-plugin",
	"license": "proprietary",
	"authors": [
		{
			"name": "ExampleVendor GmbH",
			"role": "Manufacturer"
		}
	],
	"extra": {
		"copyright": "(c) Copyright...",
		"activatePerDomain": true, // Plugin in der Agency-Version für einzelne Domains (de-)aktivierbar
		"label": {
			"en": "Really special plugin", // Anzeigename in der Pluginverwaltung
			"de": "Wirklich besonderes Plugin",
			"fr": "Plugin vraiment spécial"
		},
		"description": {
			"de": "Dieses Plugin macht etwas ganz Besonderes, das hier beschrieben werden sollte.",
			"fr": "Ce plugin fait quelque chose de vraiment spécial qui devrait être décrit ici."
		},
		"manufacturerLink": {
			"de": "https://examplevendor.example",
			"en": "https://examplevendor.example"
		},
		"supportLink": {
			"de": "https://examplevendor.example/support_de/",
			"en": "https://examplevendor.example/support_en/"
		},
		"preview": "pfad/zu/preview.png" // OPTIONAL: Wenn das Vorschaubild nicht am o.g. Standard-Ort liegt
	}
}
```

Wenn übersetzbare Angaben in einer Sprache fehlen, wird als Fallback die englische Angabe verwendet.

## Templates

Templates aus dem `templates/`-Verzeichnis des Plugins werden über Twig-Namespaces nach dem Schema `@plugin:PluginVerzeichnis/` eingebunden.

Beim obrigen Beispielplugin wäre `templates/index.html.twig` also `@plugin:ExamplevendorReallySpecialPlugin/index.html.twig`.

### Templates des Hauptsystems verändern

Um Templates anderer Menüpunkte als der eigenen zu ergänzen oder zu bearbeiten, kann das Event `App\Event\TemplateRenderEvent` verwendet werden.

Dabei können Twig-Blöcke genutzt werden um Teile des Ausgabe zu ersetzen und Template-Variablen gelesen und gesetzt werden.

```
class BackendTemplateListener implements EventSubscriberInterface
{
	private $pluginState;

	public function __construct(PluginState $pluginState)
	{
		$this->pluginState = $pluginState;
	}

	/**
	 * @return array
	 */
	public static function getSubscribedEvents()
	{
		return [
			TemplateRenderEvent::nameForView('domain/index.html.twig') => ['onRenderDomainIndex', 100],
		];
	}

	/**
	 * @return void
	 */
	public function onRenderDomainIndex(TemplateRenderEvent $event)
	{
		if (!$this->pluginState->isActiveForCurrentDomain()) {
			return;
		}

		$event->extendTemplate('@plugin:ExamplevendorReallySpecialPlugin/domain_index.html.twig');
		$event->set('someVariable', ...);
	}
}
```

## Routen und Menüpunkte

Routen und Menüpunkte können über die [`@Route`](https://symfony.com/doc/4.4/routing.html#creating-routes-as-annotations) und `@Menu`-Annotations in Controllern in `src/Controller/` erzeugt werden.
Die Abhängigkeiten für die Annotationen werden bereits vom Hauptsystem importiert.
Im Plugin müssen Sie die Annotationen also nur mit `use Symfony\Component\Routing\Annotation\Route;` und `use App\Component\Menu\Annotation\Menu;` importieren.

Routen-Namen **müssen** mit `plugin_herstellername_pluginname_` beginnen, damit die Rechteverwaltung greift und Plugin-Routen aktiviert/deaktiviert werden, je nachdem ob ein Plugin für einen User aktiviert ist. Der Plugin-Name und der Herstellerpräfix sind dabei in der gleichen snake_case-Schreibweise wie in der `composer.json` zu schreiben (nur mit Unterstrich statt Schrägstrich).

### `@Menu`-Annotation

Die `Menu`-Annotation erzeugt einen Menüpunkt zu einer Route.

Sie kann folgende Parameter haben:

* *erster Parameter* bzw. `name`: *string* Der Name der für die Anzeige des Menüpunkts verwendet wird.
  Dieser wird mit dem normalen Übersetzungssystem übersetzt.
* `group`: *string* Menügruppe in dem der Menüpunkt angezeigt werden soll (optional, standardmäßig unter "Plugins")
* `icon`: *string* Icon-Name. Derzeit werden `glyphicon-…` und `fa-…` unterstützt.
* `order`: *integer* Order-ID, mit der die Position im Menü bestimmt wird
* `route`: *string* Route zu der der Menüpunkt führen soll (Standard: wird aus der `@Route`-Annotation der
  Methode gelesen)
* `route_group`: *string* Präfix aller Routen, die zu dem Menüpunkt gehören (Standard: wird aus der
  `@Route`-Annotation der Klasse gelesen, wenn vorhanden, sonst gleich `route`). Das wird für die Anzeige,
  ob der Menüpunkt noch aktiv ist, verwendet.
* `access={…}`: *string[]* Wer Zugriff auf den Menüpunkt haben soll. Mögliche Werte sind `"admin"`,
  `"user"` und `"subuser"`. (Standard: wird aus der Superklasse der Controller-Klasse bestimmt).
* `navigation`: *string* In welcher Navigation der Menüpunkt angezeigt werden soll. Mögliche Werte sind
  `main`, `domain` und `meta`. Dabei entspricht `main` der Navigation die der Benutzer beim Einloggen
  angezeigt bekommt. Also entweder `domain` oder `meta`, je nach Edition und Benutzertyp.
  (Standard: `domain` bei `DomainDependantController`n, ansonsten `main`).
* `editions={…}`: *string[]* Editionen, in denen der Menüpunkt angezeigt werden soll. (Standard:
  `{"extended"}` für `HostingController`, ansonsten alle Editionen).
* `envs={…}`: *string[]* Environments in denen der Menüpunkt angezeigt werden soll. Z.B. `{"dev"}` für
  nur im Entwicklermodus. (Standard: alle)

### Voreinstellung der Zugriffsrechte und des Navigationsbereichs

Wenn nicht explizit mit `access` und `navigation` gesetzt, hängt es von der Klasse ab, von der der Controller ableitet,
wer wo den Menüpunkt zu sehen bekommt.

* `DomainDependantController`: In der Domain-Navigation. Nur sichtbar für Benutzer die Domainzugriff haben können (keine Agency-Admins)
* `AdminController`: In der Hauptnavigation. Nur sichtbar für Admins in der Agency-Edition und den Benutzer in der Basic-Edition.
* `HostingController`: In der Hauptnavigation. Nur sichtbar für Admins in der Agency-Edition.
* `AbstractController`: In der Hauptnavigation . Nur sichtbar für Benutzer die Domainzugriff haben können (keine Agency-Admins)
* `UniversalController`: In der Hauptnavigation. Für alle sichtbar.
* `UnrestrictedController`: In der Hauptnavigation. Für alle sichtbar.

Was die Hauptnavigation ist, unterscheidet sich je nach Edition und Benutzertyp. Es ist immer die Navigation, die nach
dem Einloggen erscheint. Also die Domain-Navigation für Basic-Edition-Nutzer und die Meta/User-Navigation für
Agency-Kunden. Bei Agency-Admins ist es wieder die "Domain"-Navigation (auch wenn es keine Domain gibt).

Beispiel:

```php
namespace Plugins\ExamplevendorReallySpecialPlugin;

use App\Component\Menu\Annotation\Menu;
use App\Controller\DomainDependantController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

/**
 * @Route("/domains/{_domainId}/plugins/examplevendor/really_special/", name="plugin_examplevendor_really_special_plugin_")
 */
class MainController extends DomainDependantController
{
	/**
	 * @Menu("Really special", icon="fa-plug")
	 * @Route("", name="index", methods={"HEAD", "GET"})
	 */
	public function index(...): Response
	{
		...
	}

	/**
	 * @Route("", name="save")
	 */
	public function indexSave(...): Response
	{
		...
	}
}
```

Das Symfony-Autowiring kann verwendet werden. Innerhalb von Plugins sind zusätzlich zwei besondere Autowiring-Argumente möglich:

- `App\Model\PluginState` liefert das Plugin-Status-Model für das aktuelle Plugin, mit dem z.B. überprüft werden kann, ob das Plugin aktiv sein soll.
- `string $PLUGINPATH` liefert den vollständigen Pfad zum Plugin-Verzeichnis.

Menüpunkte im Domain-Menü (also solche, deren Controller von `DomainDependantController` ableitet) werden automatisch ein-/ausgeblendet, wenn das Plugin für die Domain (de-)aktiviert wird.

Menüpunkte die nicht domainabhängig sind, werden in der Agency-Version automatisch ausgeblendet, wenn das Plugin für einen Kunden gesperrt wird.

Für speziellere Anforderungen ist es auch möglich Menüeinträge über einen Event-Listerner auf das Event `App\Event\MenuGenerationEvent` manuell zu setzen.

### Auf Routen anderer Controller reagieren

Mit dem Event `ccm19.controller.request.<route_name>` also z.B. `ccm19.controller.request.app_dashboard` kann auf eine Route, bevor der jeweilige Controller ausgeführt wird, reagiert werden.

Das Event-Objekt ist ein `Symfony\Component\HttpKernel\Event\ControllerEvent`. Mit der Methode `setController()` kann der Request auch auf einen anderen Controller umgeleitet werden.

Das Event `ccm19.controller.response.<route_name>` ermöglicht dagegen Code auszuführen, nachdem der Controller durchgelaufen ist.

Beide Events werden nicht bei unautorisiertem Zugriff ausgelöst, also z.B. wenn eine Route, die einen angemeldeten Benutzer erfordert, ohne gültige Session aufgerufen wird.

**Wichtig:** Bei allen Event-Handlern ist grundsätzlich mittels `$pluginState->isActiveForCurrentDomain()` bzw. je nach Kontext `$pluginState->isAllowedForCurrentUser()` zu überprüfen, ob eine Aktion des Plugins im aktuellen Kontext erwünscht ist.
