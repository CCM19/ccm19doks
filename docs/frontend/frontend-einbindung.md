# CCM19 Integrationsvarianten

Es gibt drei mögliche Varianten, wie Sie das CCM19 Cookie Consent Tool nutzen können. Prinzipiell dient das Tool dazu, die Ausführung bestimmter Skripte solange zu unterbinden, bis ein Consent / Zustimmung für die Ausführung vorliegt.

Diese Skripte können Cookies, Local-Storage-Elemente oder andere Objekte in den Browsern der Besucher speichern oder anderweitig Daten auslesen. Auf die rechtlichen Hintergründen werden wir an dieser Stelle nicht weiter eingehen, hier geht es ausschließlich um die technische Realisierung.

Jede der drei Möglichkeiten kann die Ausführung der Skripte zuverlässig blockieren, Möglichkeiten 2 und 3 verhindern auch effektiv, dass Skripte vorgeladen werden. Diese sind in der Umsetzung aber auch etwas aufwändiger.

Die Grundvoraussetzung ist jeweils, dass der CCM19-Code-Schnipsel in Ihre Seite integriert wurde; dieser Schritt wird [hier](/integrationen/ccm19-standard/) erklärt.

**Bitte wählen Sie immer nur EINE der drei Methoden zur Anwendung aus!**



## Möglichkeit 1 - Blocking

Das ist die Standard-Möglichkeit, die auch beim Onboarding-Prozess genutzt wird. Der CCM19 Scanner untersucht Ihre Seite, liest aus, welche Skripte genutzt werden, und setzt daraus den Inhalt Ihres Banners zusammen.

Hierbei muss nur der Script-/HTML-Schnipsel von CCM19 in Ihre Seite integriert werden, der Rest wird über die Benutzeroberfläche verwaltet.

Technisch betrachtet wird dabei durch CCM19 die **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt.

**Einfache Nutzung, alles in einer Oberfläche, super schnell eingerichtet. Zuverlässige Blockierung der Skripte. Keine tieferen Arbeiten im HTML / Templates der Seiten notwendig.**

Skripte können trotzdem vom Browser **geladen**, aber **nicht** ausgeführt werden. Falls der Load alleine schon Cookies setzt, kann das zu Problemen führen. Daher sollte im Anschluss auf jeden Fall kontrolliert werden, ob vor dem Consent nicht doch noch Cookies gesetzt werden, die nicht technisch notwendig sind.

<video src="../../assets/Script-Blocking%20Video%20Version%204%2016zu9.mp4"></video>



## Möglichkeit 2 - Tag Manager Funktionalität

Sie können CCM19 als vollwertigen Tag Manager nutzen, der die Skripte innerhalb von CCM19 verwaltet und diese auch erst nach Consent lädt und ausführt.

Dazu tragen Sie den HTML-Code, z.B. das Google Analytics Skript, im CCM19 bei der passenden Einbindung im Feld "Quellcode der Einbindung" ein und entfernen den Code dafür aus dem HTML Ihrer Seite. Wo und wie Sie das durchführen, hängt von Ihrem CMS / Shop System ab. Oft kann man diese Skripte auch über die CMS Oberfläche deaktivieren.

Technisch betrachtet wird dabei durch CCM19 das  **Laden** UND die  **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt. Es ist also eine sauberere Methode, die außerdem den Vorteil hat, dass sie sich positiv auf die Ladegechwindigkeit der Seite auswirkt, weil Skripte nur noch geladen werden müssen, wenn Consent vorliegt.



## Möglichkeit 3 - HTML Manipulierung

Sie können CCM19 auch nutzen, um im Quelltext blockierte Skripte via Consent freizugeben und ausführen zu lassen.

Um dies zu nutzen, können Sie Ihren Skripten unseren CCM19-spezifischen Wert für das `type`-Attribut vergeben. Verwenden Sie des Weiteren nicht das `src`-Attribut zur Angabe der Skript-URL, sondern `data-ccm-loader-src`. Durch diese Anpassung erkennt ein Browser das entsprechende Skript nun nicht mehr als auszuführenden Javascript-Code und lässt von der Verarbeitung dessen zunächst ab.

CCM19 ist in der Lage, Skripte diesen Typs zu verarbeiten und gibt das Skript zum Laden frei, sofern laut Ihrer CCM19-Konfiguration nichts dagegen spricht.

**Unser Typ-Attribut sieht so aus: `type="text/x-ccm-loader"`**

Verwenden Sie diesen Wert für jedes `script`-Tag Ihrer Seite, das entsprechend dieser Funktion geblockt bzw. freigegeben und nachgeladen werden soll. Exemplarisch sieht das Ganze dann so aus:

```javascript
<script data-ccm-loader-src="https://your.site/script.js" type="text/x-ccm-loader"></script>
```

#### Gruppe für den Script-Loader

Haben Sie Ihre Skripte auf der Website mit unserem Typ-Attribut `type="text/x-ccm-loader"` manuell ausgestattet, können Sie mit dieser Funktion diese Skripte gruppieren und einheitlich blockieren.

Den Gruppennamen definieren Sie pro Einbindung selbst und fügen diesen ebenfalls dem entsprechenden Skript hinzu. Die Gruppenbezeichnung besteht immer aus folgendem Teil: `data-ccm-loader-group="beispiel_bezeichnung"`.

Zusammen mit dem `type`-Attribut sieht es dann so aus:

```javascript
<script data-ccm-loader-src="https://your.site/script.js" type="text/x-ccm-loader" data-ccm-loader-group="beispiel_bezeichnung"></script>
```

Tragen Sie den Gruppennamen in der relevanten Einbindung unter dem Punkt "Gruppe für den Script-Loader" ein, um die Einbindung mit den markierten Skripten Ihrer Webseite zu verknüpfen.

Sobald ein Seitenbesucher eine solche Einbindung zulässt, werden die gruppierten Skripte nachgeladen.

Technisch betrachtet wird dabei durch CCM19 das  **Laden** UND die  **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt.

**Diese Variante gibt den Benutzer die meisten Flexibilität, da so auch individuelle Skripte mit speziellen Funktionen die z.B. nur auf einer Seite vorkommen gesteuert werden können.**