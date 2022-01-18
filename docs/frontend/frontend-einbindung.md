# CCM19 nutzen

Es gibt 3 mögliche Varianten wie Sie das CCM19 Cookie Consent Tool nutzen können. Prinzipiell dient das Tool dazu die Ausführung bestimmter Skripten solange zu unterbinden bis ein Consent / Zustimmung für die Ausführung vorliegt.

Diese Skripte können Cookies, Local Storage Elemente oder andere Objekte in den Browsern der Besucher speichern oder anderweitig Daten auslesen. Zu den rechtlichen Hintergründen sagen wir hier nichts, hier gehts um die technische Realisierung.

## Möglichkeit 1 - Blocking

Das ist die Standard Möglichkeit die auch beim Onboarding Prozess genutzt wird. Der CCM19 Scanner untersucht Ihre Seite, liest aus welche Skripte genutzt werden und setzt daraus dem Inhalt Ihres Banners zusammen.

Hierbei muss nur der Script / HTML Schnipsel von CCM19 in Ihre Seite integriert werden, der Rest wird über die Benutzeroberfläche verwaltet.

Technisch betrachtet wird dabei durch CCM19 die **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt.

### Vorteil

Einfache Nutzung, alles in einer Oberfläche, super schnell eingerichtet. Zuverlässige Blockierung der Skripte. Keine tieferen Arbeiten im HTML / Templates der Seiten notwendig.

### Nachteil

Skripte können trotzdem vom Browser **geladen** aber **nicht** ausgeführt werden. Falls der Load alleine schon Cookies setzt, kann das zu Problemen führen. Daher sollte das auf jeden Fall beobachtet und kontrolliert werden.



## Möglichkeit 2 - Tag Manager Funktionalität

Sie können CCM19 als vollwertigen Tag Manager nutzen, der die Skripte innerhalb von CCM19 verwaltet und diese auch erst nach Consent lädt und ausführt.

Dabei tragen Sie z.B. das Google Analytics Skript im CCM19 ein und entfernen dieses aus dem HTML Ihrer Seite. Wo und wie Sie das durchführen, hängt von Ihrem CMS / Shop System ab. Oft kann man diese Skripte auch über die CMS Oberfläche deaktivieren.

Technisch betrachtet wird dabei durch CCM19 das  **Laden** UND die  **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt.



## Möglichkeit 3 - HTML Manipulierung

Sie können CCM19 auch nutzen um im Quelltext blockierte Skripte via Consent freizugeben und ausführen zu lassen.



Technisch betrachtet wird dabei durch CCM19 das  **Laden** UND die  **Ausführung** der Skripte unterbunden, solange bis ein Consent für die Ausführung vorliegt.

