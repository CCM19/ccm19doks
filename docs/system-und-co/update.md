# Updates


Durch die Update-Funktion bekommen Sie immer die aktuellste und neuste stable-Version des CCM19 Tools. Im Changelog können Sie sehen, was für Änderungen vorgenommen wurden. 


![screenshot-2020.09.30-14_59_11-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-14_59_11-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



## Automatische Updates

Durch das Aktivieren der Funktion "Automatische Updates aktivieren" wird Ihr CCM19-System automatisch aktualisiert.



## Beta-Version

Sie haben die Möglichkeit – absolut auf eigene Verantwortung und **ohne** Support – am Beta-Kanal teilzunehmen. Öffnen Sie dazu den Menüpunkt „Update“ und drücken Sie nacheinander die folgenden Tasten Ihrer Tastatur: <kbd>↑ ↑ ↓ ↓ ← → ← → B A</kbd>

Danach taucht folgender Eintrag auf:


![screenshot-2020.09.30-15_03_22-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-15_03_22-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Wählen Sie hier aus dem Selectfeld "Beta" aus und drücken sie auf Speichern. Sie sind ab jetzt im Beta-Channel für die Verteilung von Updates und Upgrades.

# Fehler nach Updates (sehr selten)

Falls nach einem Update kryptische Fehlermeldungen auftauchen ist der erste Schritt das Löschen des Caches -> [Cache bearbeiten](caching.md). Das kann in sehr seltenen Fällen passieren wenn Zugriffe auf irgendeine Art auf dem Server schief laufen.


Normalerweise wird das auch automatisch nach einem Update durchgeführt, mitunter kommt es aber unter bestimmten Bedingungen zu einem Abbruch - so dass der Cache nicht komplett gelöscht werden kann. Da hilft dann das manuelle betätigen.

> Falls es dann immer noch nicht geht muss man tatsächlich auf die FTP Ebene gehen und manuell das Verzeichnis `CCM19Verzeicnis/www/var/cache/prod` löschen, also das gesamte Verzeichnis `prod`. Das wird dann beim nächsten Aufruf von CCM19 automatisch direkt wieder neu erstellt, hier kann man keine relevanten Daten löschen.


Falls es dann immer noch nicht geht - Fragen Sie bitte beim Support nach, wir bekommen das Problem dann für Sie gelöst!

 
