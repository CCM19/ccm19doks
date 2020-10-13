# Frontend Widgets

Das Frontend von CCM19 besteht aus den Widgets die Sie sehen und bedienen können und den Funktionen im Quellcode die das Skript umsetzt, um die notwendigen Funktionen zu realisieren. Im Folgenden werden wir alle Punkte durchgehen und alle Fenster zeigen die das CCM19 erstellt.



## Performance der Widgets

Das Widget und alle anderen Daten werden minifiziert, komprimiert und serverseitig gechached um einen bestmögliche Performance zu erreichen. 

Durchschnittliche Ladezeiten unseres Skriptes betragen zwischen 0,2 und 0,4 Sekunden pro Aufruf, dies ist im Schnitt für diese Skripte eine sehr gute Ladezeit - auch im Vergleich zum Mitbewerb.

> Wenn Sie eine Download Version verwenden wird die Aufrufzeit durch Ihren Server wesentlich mitbestimmt. In der Regel ist aber auch bei fast allen Server gewährleistet dass ein schneller Aufruf möglich ist.



## Primäres Widget

Dies ist das erste Widget was die Besucher Ihrer Webseite zu sehen bekommen. Daher ist es wichtig dass Sie es optimal an das Look & Feel Ihrer Webseite anpassen. Wie Sie das machen lesen Sie hier: [Themes](../funktionen/themes.md) - grundsätzlich lassen sich alle Widgets komplett individualisieren und positionieren:

* Mittig

* Links

* Rechts

* Oben

* Unten

  

![screenshot-2020.09.30-16_13_37-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-16_13_37-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Der Klick auf "Alles akzeptieren" akzeptiert alle eingestellten Skripte und Cookies und schließt das Fenster sofort. Der Consent wird dabei im Browser der Besucher gespeichert.

### Consent bleibt erhalten

Der Consent bleibt solange erhalten wie der Besucher die Cookie oder Local Storage Daten in seinem Browser nicht löscht. Die maximale Laufzeit stellen Sie hier [Consentspeicherung](../system-und-co/consent-speicherung.md) ein.  Bei einem weiteren Aufruf der Seite wird die Maske nicht mehr gezeigt.

## Einstellungen

Klickt der Besucher auf den Button Einstellungen erreicht er die nächste Maske wo er die Kategorien der Einbindungen, Skripte und Cookies anschauen, durchlesen und bestätigen kann.

 ![screenshot-2020.09.30-16_15_54-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-16_15_54-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Die Kategorie "Technisch notwendig" oder auch "Technisch notwendig / Essentiell" ist immer angehakt und kann nicht abgehakt werden. 

Hier werden nur die Einbindungen und Cookies beschrieben die für das Funktionieren der Webseite unabdingbar sind oder für die nach $6 DSGVO ein begründetes Interesse des Betreibers besteht. Auf die rechtlichen Implikationen wollen wir an dieser Stelle lieber nicht eingehen.

Die Besucher können nur diese Haken setzen oder nicht. Klicken die Besucher auf Speichern wird der Zustand wie er angezeigt wird, gespeichert. Klickt man hier auf "Alle Akzeptieren" werden alle Kategorien mit allen sich darin befindenden Einbindungen akzeptiert.

### Informationen zu den Kategorien

Die einzelnen Kategorien können auch Zusatztexte bekommen, diese können Sie in der Administration pflegen, Beispiel siehe im folgenden Screenshot.

![screenshot-2020.09.30-20_21_46-BGH konformer Cookie Banner - Cookie Consent Manager - Cookie Consent Management Software - mandatenfähig, multidomain](../assets/screenshot-2020.09.30-20_21_46-BGH%20konformer%20Cookie%20Banner%20-%20Cookie%20Consent%20Manager%20-%20Cookie%20Consent%20Management%20Software%20-%20mandatenf%C3%A4hig,%20multidomain.jpg)



## Mehr Informationen

Wenn Besucher mehr Informationen über die einzelnen Einbindungen lesen möchte dann können sie auf das Fragezeichen klicken und kommen dann in die folgende Maske.

![screenshot-2020.09.30-16_39_00-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-16_39_00-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Hier können die Besucher nun alle Elemente die auf der Webseite verwendet im Detail nachlesen, was machen die Skripte, was wird wohin gespeichert, wer hat Zugriff darauf usw. Diese Einstellungen können Sie hier anpassen:  [Embeddings & Cookies](../funktionen/cookies-und-andere.md) .#

In der linken Spalte sehen Sie die Einbindungen sortiert nach Kategorien, jeder Eintrag kann angeklickt werden und die Besucher springen dann direkt zu dem passenden Eintrag um weitere Informationen zu bekommen. Die Besucher können jeder einzelnen Einbindung oder auch kategorieweise der Nutzung zustimmen.



## Einfacher Widerruf oder Änderung - Konfigurationsbox öffnen

CCM19 bietet den Besuchern eine einfache Möglichkeit den Consent jederzeit zu widerrufen oder anzupassen. Als Betreiben können Sie das unten stehende Icon einfach einblenden lassen, ein Klick auf dieses Icon öffnet wieder die Consent Maske - so dass Ihre Besucher dort wieder Ihre Einstellungen anpassen können.



![screenshot-2020.09.29-13_59_03-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_59_03-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



## Konfigurationsbox erneut öffnen per Link

Sie möchten Ihren Besuchern die Möglichkeit geben, sich nachträglich noch umzuentscheiden und z.B. doch keine Analyse-Cookies zuzulassen? Fügen Sie einfach folgendes HTML Snippet ein:

``` html
<a href="#" onclick="CCM.openWidget();return false;">Konfigurationsbox öffnen</a>
```

Somit wird beim Klick auf diesen Link das Konfigurations Pop-Up erneut für den Besucher geöffnet.

Alternativ, falls Sie keine Javascript-Links einfügen können, können Sie das folgende Ziel in einem Link verwenden: **#CCM.openWidget**.

```html
<a href="#CCM.openWidget">Konfigurationsbox öffnen</a>
```



## Weitere Möglichkeiten der Steuerung im Frontend

Weitere Möglichkeiten finden Sie hier -  [Javascript / programmatische Steuerung](../api/javascript-apis.md) 



## Impressum im Frontend

Das Impressum können Sie entweder per Link oder direkt einbinden - wie das funktioniert lesen Sie hier nach:  [Impressum bearbeiten](../funktionen/impressum.md) . Die Maske im Frontend sieht dann so aus:

![screenshot-2020.09.30-12_51_32-BGH konformer Cookie Banner - Cookie Consent Manager - Cookie Consent Management Software - mandatenfähig, multidomain](../assets/screenshot-2020.09.30-12_51_32-BGH%20konformer%20Cookie%20Banner%20-%20Cookie%20Consent%20Manager%20-%20Cookie%20Consent%20Management%20Software%20-%20mandatenf%C3%A4hig,%20multidomain.jpg)



## Datenschutz im Frontend

Die Datenschutzerklärung erreichen Sie wenn Sie auf den Link "Datenschutzerkläriung" klicken, bearbeiten können Sie die Daten hier:  [Datenschutz bearbeiten](../funktionen/datenschutz.md) 



![screenshot-2020.09.30-13_03_09-BGH konformer Cookie Banner - Cookie Consent Manager - Cookie Consent Management Software - mandatenfähig, multidomain](../assets/screenshot-2020.09.30-13_03_09-BGH%20konformer%20Cookie%20Banner%20-%20Cookie%20Consent%20Manager%20-%20Cookie%20Consent%20Management%20Software%20-%20mandatenf%C3%A4hig,%20multidomain.jpg)