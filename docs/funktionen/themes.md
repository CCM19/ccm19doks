---
title: Themes
---

# Themes einrichten und nutzen

CCM19 ist komplett themefähig - d.h. Sie können alle Elemente des Frontends optisch anpassen. Sie können beliebig viele Themes ausprobieren. 

Wenn Sie auf den Menüpunkt Themes klicken sehen Sie zuerst die Übersicht der vorhandenen Themes.



![screenshot-2020.09.29-13_27_27-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_27_27-CCM19%20-%20Cookie%20Consent%20Management%20Software.png)

Der Klick auf das grüne Stiftsymbol leitet Sie in die Bearbeitungsmaske, der rote Papierkorb löscht Ihr Theme ( nach Nachfrage ), der Klick auf die doppelten grünen Ordner kopiert das vorhandene Theme. 

Mit dem Klick auf das blaue Icon setzen Sie das Theme als Standard für das Frontend.

## Neues Theme anlegen

Wenn Sie ein neues Theme anlegen wollen können Sie zum einen auf den Button "Erstellen" klicken oder Sie kopieren ein vorhandenes Theme und passen dieses an. Das Kopieren ist das von CCM19 empfohlene Vorgehen - auch für individuelle Anpassungen an vorhandenen Themes. Auf diese Weise haben Sie immer ein Fallback zur Hand.

## Layout / Theme anpassen

In jedem Theme können Sie mit Hilfe von einigen Buttons und Einstellmöglichkeiten das Theme definieren. Darüber hinaus haben Sie die Möglichkeit, mit Hilfe von CSS-Anweisungen jedes optische Detail anzupassen, die komplette Frontendmaske ist per CSS erreichbar.

![screenshot-2020.12.17-14_24_47-1608211487460](../assets/screenshot-2020.12.17-14_24_47-1608211487460.jpg)

Verwenden Sie bei den Individuelle CSS Einstellungen im Zweifel !important um Einstellungen Ihres CMS Systems zu überschreiben. In der Oberfläche können Sie einiges einstellen. Die Einstellungen die Sie hier sehen, resultieren in dem folgenden Frontend.

## Vorschau

Über den Button Vorschau können Sie sich eine Vorschau des Frontend Widgets anschauen. Der Klick öffnet nicht Ihre Seite sondern eine Seite im Inneren des CCM19 Adminbereiches. Nach jeder Änderung des Layouts ist ein Neuladen erforderlich. Das Widget ist voll funktionsfähig - d.h. Sie können alle Elemente des Widgets optisch anpassen und testen.



![screenshot-2020.09.29-13_42_42-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_42_42-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Vorschau mit Widget.



## Frontend Overlay - Cookie Hinweis Box

![Frontend Light Version](../assets/images/10-frontend-light.png)

Frontend Light Version

Die Buttons und Hintergrundfarben die Sie in der Administration einstellen, kommen direkt im Frontend an. Sie können ebenfalls die Links Impressum und Datenschutzerklärung optisch anpassen.

## Buttons & Einstellungen

Weiterhin gibt es die folgenden Buttons:

### Position

Hier positionieren Sie das Overlay im Frontend, Sie können folgende Einstellungen wählen:

* links
* rechts
* oben
* unten
* mittig

### Auswahltyp

Sie können Häkchen oder Schalter definieren für die Ansicht in den Kategorien und einzelnen Einbindungen.

#### Häkchen



![screenshot-2020.09.29-13_53_33-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_53_33-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

#### Schalter

![screenshot-2020.09.29-13_54_35-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_54_35-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Die Farben können Sie natürlich über die individuellen CSS Einstellungen anpassen.

### Kategorien im Hauptfenster anzeigen

Diese Option platziert alle Kategorien im Hauptfenster zur Schnellauswahl.

- Eine neue Schaltfläche "Speichern" erscheint neben "Alle akzeptieren" und "Ablehnen". (falls letztere aktiv ist)

- Um mit dem Platz des Widgets zurechtzukommen, wird die Schaltfläche "Einstellungen" entfernt und durch einen einfachen Textlink unter den übrigen Schaltflächen ersetzt.

  

  ![screenshot-2020.09.29-13_56_09-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_56_09-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Blockierend

Blockierend bedeutet dass wie auf dem Screenshot zu sehen ist die Seite im Hintergrund blockiert ist und erst wenn sich ein Besucher definitiv entschieden hat ob er die [Cookies](https://www.ccm19.de/glossar/13-Cookies.html#13) akzeptiert oder nicht wird er auf die Seite gelassen.

### Einstellungsicon anzeigen

Wenn dieser Haken gesetzt ist wird nach dem Consent über die Seite ein Einstellungsicon per Javascript gesetzt. Auf diese Weise kann der von der DSGVO geforderter Widerruf einfachst möglich gesetzt werden. Das Icon wird standardmäßig links unten in die Ecke platziert.

![screenshot-2020.09.29-13_59_03-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_59_03-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Cookies ablehnen

Die DSGVO fordert eine einfache Möglichkeit das Setzen von Cookies und die Nutzung von Skripten zu widersprechen. Daher gibt es diesen Button. Ist der Haken gesetzt - dann wird der Ablehnen Button direkt in der 1. Maske angezeigt.



![screenshot-2020.09.29-14_00_58-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-14_00_58-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Do not Track Respekt

Wenn diese Einstellung angehakt wird - dann wird automatisch die Do not Track Einstellung im Browser respektiert und umgesetzt - d.h. es werden keine Tracking Cookies gesetzt, nur technisch notwendige Elemente werden geladen.

### Nur in der EU anzeigen

Mit dieser Einstellung können Sie festlegen dass der Cookie Hinweis nur Besuchern aus der EU angezeigt wird. Die Auflösung erfolgt anhand der verwendeten IP des Besuchers und kann daher nicht 100%ig genau sein. Bei Besuchern aus anderen Ländern werden alle Cookies aktiviert, außer wenn der Besucher „Do Not Track“ signalisiert und „Do Not Track respektieren“ aktiviert wurde.

Dieses Produkt enthält GeoLite2-Daten von MaxMind, verfügbar auf [https://www.maxmind.com](https://5f3c395.ccm19.de/app/public/themes/&guot;https://www.maxmind.com&guot;).

### Manipulationsschutz

Verhindert simulierte Klicks auf die Akzeptieren-Buttons, um die Cookie-Auswahl des Nutzers zu schützen. **Deaktivieren Sie diese Funktion nicht, wenn Sie sich nicht sicher sind, dass es unbedingt notwendig ist. Dies könnte Ihre rechtliche Position beim Beweisen, dass Consent erteilt wurde, schwächen.**

### "Alle akzeptieren"-Button anzeigen im Fenster Kategorien

Mit dieser Einstellung wird im Kategorien Fenster der "Alles Akzeptieren" Button zusätzlich angezeigt.

![screenshot-2020.09.29-14_03_37-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-14_03_37-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Logo des Seitenbetreibers

Hier laden Sie Ihr Logo hoch das im Frontend - also Ihre Webseite - im Overlay angezeigt wird. Im obigen Screenshot sehen Sie dort das Logo von ccm19 - das können Sie gegen Ihres tauschen.

### Logo anzeigen

Damit können Sie einstellen ob das Logo im Frontend im Overlay angezeigt werden soll.

### Powerd By CCM19 entfernen

Hier geht es um den Link im Frontend Overlay, der rechts unten steht. Dies ist ein Link der auf die CCM19 Seite verlinkt. Dieser kann durch setzen dieses Hakens entfernt werden. Allerdings ist dies nur möglich wenn vorher eine Whitelabel Lizenz für diese Installation erworben wurde.

### Farben

Hier stellen Sie für die verschiedenen Buttons und Hintergründe im Frontend die Farben ein - achten Sie hier darauf dass auch Rahmen teilweise davon abhängen, wenn Sie einen weißen Rahmen auf weißem Hintergrund setzen mit weißer Schrift sehen Sie natürlich nichts mehr. Am besten kontrollieren Sie jede Änderung einmal im Frontend indem Sie das Overlay neu aufrufen!

### CSS

Hier können Sie komplett individuelles CSS eintragen - für die einzelnen Elemente schauen Sie bitte in den Seiteninspektor Ihres Browsers. Im Zweifel müssen Sie Einstellungen per “!important” überschreiben - **Beispiel:**

``` css
.ccm-root button  
{ 
    border:1px solid #c2bcbc; 
} 
.ccm-control-panel--purpose > input[type="checkbox"] + label 
{ 
	color:#ccc;
} 
.ccm-modal--footer 
{ 
    background-color:#26282f; 
}       
 
```

### Individuelles CSS Iframeblocker

Hier können Sie für den iframe Blocker individuelle CSS Anweisungen vergeben, spezielle Hintergrundbilder usw. Man kann die geblockte Domain als Klasse vergeben, um dann gezielter CSS definieren zu können. 
Beispiel:
\- Blockiert wird ``https://www.google.com/maps/…``
\- Im Iframe erhält das HTML-Element die Klasse z. B. wie folgt: ``domain--www-google-com``
\- Mögliches CSS

~~~css
```
html.domain--www-google-com body {
    background-image: url('google-maps-placeholder.jpg');
}
html.domain--www-facebook-com body {
    background-image: url('facebook-placeholder.jpg');
}
~~~