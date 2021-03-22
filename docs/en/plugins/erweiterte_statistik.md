# Erweiterte Statistik

Mit Hilfe der erweiterten Statistik können Sie die statistischen Consent Daten weiter auswerten. Die Daten liegen hier vollständig anonymisiert vor - ein Rückschluß auf individuelle Datensätze ist nicht möglich.

## Übersicht der Statistik

Hier sehen Sie die Daten einer Beispielseite von einer unserer vielen Kundenseiten die uns freundlicherweise zur Verfügung gestellt wurden. 

![screenshot-1615194809151-151](../assets/screenshot-1615194809151-151.jpg)



## Nutzung der Maske

Oben links können Sie auswählen ob die Daten absolut - also die reinen Zahlen oder prozentual dargestellt werden sollen.

Die prozentualen Werte stehen aber für die Vergangenheit aber nur für einige kurze Zeiträume zur Verfügung da sehr lange nur die Zustimmungen geloggt wurden, aber keine Einblendungen. Die wurden jeweils nur für den jeweiligen Monat für die Abrechnung gezählt und dann verworfen wurden. Zusätzlich gab es noch eine Umstellung im Januar die die Zählung der Einblendungen ebenfalls gestört hat. Lediglich die Zahl der Consents ist über die Zeit hinweg belastbar - da diese direkt aus dem Consent Log kommen. Die Ursache liegt hier in den verschiedenen Experimenten die wir im Hintergrund mit den Zahlen durchgeführt haben.

Wenn keine prozentualen Werte vorliegen, wird jeweils eine 0 angezeigt.

## Zeitraum auswählen

Sie können über die beiden Auswahlfelder oben rechts den Zeitraum auswählen und die Kummulation auf Tage, Wochen, Monate oder Jahre.



## Interpretation der Daten

Die Interpretation ist etwas zeitabhängig da die Funktionen im CCM19 sich im Laufe der Zeit geändert haben (s.o.). Wie oben erwähnt sind die bis Ende Februar 2021 gezählten Einblendungen nicht immer zuverlässig, da noch experimentell. Prinzipiell ist es nun so dass die Zahl der Einblendungen sich aus allen Einblendungen der Maske berechnet, auch die Besucher die direkt wieder abspringen und die Maske nicht betätigen werden mit gezählt, außerdem alle die mit der Maske interagieren.

## Bitte beachten

Die Zahl der Einblendungen ist nur eine Teilmenge der Zahl der Nutzungen von CCM19. Das Skript läuft bei **jedem** Seitenaufruf durch da immer überprüft werden muss ob ein Consent vorliegt oder nicht. Nur wenn kein Consent vorliegt wird die Maske ausgegeben und es kommt zu einer Zählung in der obigen Anzahl der Einblendungen.