# CCM19 Upgrade auf Generation 2

Mit dem Release der Version 13.10.2020 wurde das CCM19 Cookie Consent Tool auf die Darstellung und Verarbeitung von Einbindungen statt der Nutzung von "nur" Cookies umgebaut. 

> Die alte Variante Generation 1 wird noch mindestens bis Ende 03.2021 gepflegt, erhält aber in der Regel keine neuen Funktionen mehr sondern nur noch Bugfixes.

In der alten Consentmaske konnte man nur Kategorien bestätigen oder ablehnen, mit der neuen Version kann man nun nicht nur die Kategorien abhaken, sondern auch die einzelnen Einbindungen. 

> Google Analytics ist ein gutes Beispiel. Musste man vorher jedes Cookie extra eintragen, reicht es nun einen Eintrag Google Analytics aus der Datenbank auszuwählen und dann sind direkt alle Cookies und Elemente mit angelegt. Dies Besucher können dann wählen ob sie Google Analytics nutzen wollen oder nicht.

Wenn Sie bisher eine alte Version der Generation 1 benutzt haben, dann können Sie ein manuelles Upgrade auf die Generation 2 durchführen. Ein automatisches Upgrade ist leider nicht möglich, da wir nicht alle Cookies und Zusammenhänge kennen.

> Aber keine Angst - das Upgrade ist eigentlich recht simpel zu machen und dauert in der Regel ca. 5 Minuten



## Upgrade durchführen

Um das Upgrade durchzuführen gibt es 2 Wege.

1. Umstellung der Software per Auswahl, dann müssen die Einträge neu manuel angelegt werden
2. Upgrade per erweitertem Onboarding - dann kann fast alles automatisch erfolgen.

### 1. Umstellung per Auswahl

Um die Umstellung manuell durchzuführen, gehen Sie zum Menüpunkte Frontend Verhalten links im Menü. Dort finden Sie nun den neuen folgenden Eintrag. Haken Sie zuerst den rot markierten Haken ab und lesen Sie genau was dort steht ;-).

![screenshot-2020.10.13-16_13_17-1602598397786](../assets/screenshot-2020.10.13-16_13_17-1602598397786.jpg)

Anschließend können Sie das Selectfeld von Cookie (veraltet) auf Embeddings umstellen. Sobald Sie das gemacht haben, wird der Menüpunkt Cookies durch den Menüpunkt "Einbindungen und Cookies" ersetzt und es steht eine neue Maske zur Verfügung.

Gleichzeitig wird im Frontend die Maske für den Consent ebenfalls umgestellt. Die neuen Embeddings können Sie nun unter diesem Menüpunkt erstellen, [das wird hier erklärt](../funktionen/cookies-und-andere.md). 



### 2. Umstellung via erweitertem Onboarding

Die Umstellung über das erweiterte Onboarding erreichen  Sie über den alten Menüpunkt Cookies. Damit das funktioniert sollten Sie die Umstellung unter 1 noch nicht durchführen.



![screenshot-2020.10.13-16_21_04-1602598864641](../assets/screenshot-2020.10.13-16_21_04-1602598864641.jpg)



Klicken Sie dafür auf den Link "Klicken Sie hier um das Upgrade durchzuführen." Sie gelangen dann in die schon bekannte Maske aus dem Onboarding.

![screenshot-2020.10.13-16_23_15-1602598995503](../assets/screenshot-2020.10.13-16_23_15-1602598995503.jpg)

Bei der Downloadversion muss nun die aktuell verwendete Seitenurl eingetragen werden, in unserer Cloud Version ist das nicht notwendig, hier ist die die Domain dann schon mit der Auswahl bekannt. Folgen Sie dann den Anweisungen auf dem Bildschirm, nach dem Scan kommen Sie zur gewohnten Maske und dem Ablauf der [bereits hier beschrieben ist](onboarding-schritt-1.md). 

> Wenn Sie mit dem Onboarding Ablauf durch sind landen Sie in der Auflistung der Embeddings die Sie dann wieder bearbeiten können.  [So wie hier beschrieben](../funktionen/cookies-und-andere.md).

 























