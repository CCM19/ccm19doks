# Skripte, Cookies und Einbindungen

Mit CCM19 können Sie Ihren Besuchern die rechtliche notwendige Möglichkeit geben, selber zu entscheiden welche Daten über die Besucher erhoben werden.

Damit dies funktioniert müssen alle relevanten Daten im CCM19 zur Verfügung stehen und die Einbindungen müssen getestet werden. Auch wenn CCM19 viel übernehmen kann an automatischen Tests - bleibt es doch immer dem Betreiber überlassen sämtliche Funktionen zu überprüfen. 

Eine Übersicht über vorhandene Einbindungen finden Sie unter dem Menüpunkt "Einbindungen & Cookies".

## Übersicht über die vorhandenen Einbindungen

![screenshot-2020.09.29-16_01_49-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_01_49-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Hier sehen Sie aufgelistet welche Einbindungen auf Ihrer Seite verwendet werden. Sie erkennen auf einen Blick welche Einbindungen aktiv sind, wie sie heißen und von wem diese sind.

Mit dem Klick auf das grüne Symbol kommen Sie in den Editiermodus, der Klick auf den roten Papierkorb löscht nach Nachfrage einen Eintrag.

Der Button "Neuen Eintrag erstellen" führt Sie zur Erstellungsmaske. Sinnvoller ist in der Regel der blaue Button "Eintrag aus Datenbank auswählen". Hier verbindet sich Ihre CCM19 Instanz mit unserer zentralen Datenbank und listet Ihnen die verfügbaren Einträge auf.

## Verfügbare Einbindungen

![screenshot-2020.09.29-16_05_01-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_05_01-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Hier sehen Sie aufgelistet die Einträge aus unserer Datenbank die Ihnen zur Verfügung stehen. Klicken Sie auf den grünen Button übernehmen um die Daten in die Bearbeitungsmaske zu übernehmen.

Mitunter ist noch eine Anpassung an Ihr Unternehmen oder Webseite notwendig, dies sollten Sie überprüfen damit auch rechtlich alles auf der sicheren Seite ist.

## Bearbeitungsmaske der Einbindungen

![screenshot-2020.09.29-16_07_45-CCM19 - Cookie Consent Management Software (1)](../assets/screenshot-2020.09.29-16_07_45-CCM19%20-%20Cookie%20Consent%20Management%20Software%20(1).jpg)

In der Bearbeitungsmaske können Sie folgendes eintragen:

### Name der Integration / Einbindung

Der Name der Einbindung - das kann z.B. Google Analytics sein oder Facebook Pixel. Hier sollten Sie einen aussagekräftigen Namen nutzen.

### Zweck

Hier tauchen wieder die schon oben genannten Kategorien auf. Sie können damit jeden Eintrag jeder beliebigen Kategorie zuweisen. Beachten Sie bitte aber dass Sie die rechtlichen Rahmenbedingungen beachten. Facebook Pixel z.B. wird sicher kaum unter technisch notwendig korrekt einsortiert sein.

### Aktivieren

Hiermit aktivieren Sie den Eintrag, so dass er auch im Frontend abgehakt werden kann

### Quellcode der Einbindung

Beim Quellcode der Einbindung müssen Sie den Code einfügen, durch den die Einbindung generiert wird. In unserem Beispiel wäre dies der Google Analytics-Code. **Wenn Sie einen Code einfügen, muss dieser einmalig sein und darf in keinem anderen Cookie eingetragen werden. **

> **Außerdem muss er aus dem direkten Webseitentext entfernt werden, da Sie den Code ansonsten doppelt einbinden würden. Das führt zu technischen Problemen!**



### Anbieter

Der Anbieter - hier muss der Firmenname des Anbieters rein der das Skript anbietet. In unserem Fall wäre es Google Ireland Limited. Tragen Sie hier auch gerne direkt die komplette Adresse des Unternehmens ein.

### Skripte blockieren.

Hier können Sie Skripte die im Quelltext Ihrer Seite eingebunden sind durch CCM19 blockieren. Nutzen Sie z.B. Google Analytics:

```javascript
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-123456789-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-123456789-2');
</script>
```

Dann tragen Sie in dem Feld z.B. "googletagmanager.com" ein - damit wird dann auf Ihrer Seite jedes Javascript geblockt dass diese Zeichen (String) enthält und das Skript wird nicht ausgeführt solange kein Consent gegeben wurde.

Auf diese Weise müssen Sie nicht zwingend Ihre Seite umbauen.



## Einträge je Sprache

![screenshot-2020.09.29-16_25_04-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_25_04-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Für jede verwendete Sprache können die folgenden sprachabhängigen Inhalte noch erstellt werden.

### Beschreibung 

Bei der Beschreibung tragen Sie die Aufgabe der Einbindung ein. Wieso wird diese gesetzt? Was macht diese Einbindung?

### Datenschutz-Link

Hier gehört der Link zu den Datenschutzbestimmungen des Anbieters hinein. Diesen finden Sie in der Regel wenn Sie auf die Webseite des Anbieters gehen.

### Welche Daten werden gesammelt?

Welche Daten werden ganz genau gesammelt? Nur die IP? Oder auch Klickdaten, Daten des Browsers, Logins, Verhalten uvm? Informieren Sie sich genau bei dem Anbieter des Skriptes und tragen Sie möglichst genau ein was mit den Daten passiert. Nur so ist eine informierte Einwilligung Ihrer Besucher möglich.

### Zu welchem Zweck werden die Daten gesammelt?

Warum sammeln Sie diese Daten? Was wollen Sie damit machen? Conversionoptimierung? Nutzererfahrung verbessern? Oder nur eine Warenkorb Funktion realisieren? 

### Rechtliche Grundlage

Hier definieren Sie die rechtliche Grundlage aufgrund dessen Sie diese Einbindung vornehmen wollen. Bei Tracking Skripten greift in der Regel nur "Einwilligung, Art. 6 Abs. 1 lit. a DSGVO" - Einwilligung des Besuchers durch eine informierte Entscheidung. Also rein freiwillig.

### Ort der Verarbeitung

Wo werden die Daten verarbeitet. Hier gilt nicht nur die die Adresse Ihres Büros sondern auch wo steht der Server? Berücksichtigen Sie bitte auch das Sie derzeit keine Daten in unsichere Drittländern übertragen dürfen. Anbieter die Daten in die USA exportieren sind derzeit rechtlich vermutlich nicht möglich (Stand 29.09.2020).

## Liste der Cookies und Storage Elemente

![screenshot-2020.09.29-16_26_27-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_26_27-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Hier sind alle Cookies und Storage Elemente aufgelistet die das Skript setzt. Sie können von Hand noch weitere Elemente eintragen, da der automatische Scan nicht immer alle Daten finden kann. Z.B. kann der Scanner keine Daten finden für einen eingeloggten Zustand. Auch die von CCM19 handgepflegte Datenbank muss nicht vollständig sein - überprüfen Sie die Daten immer genau.

#### Name

Die Bezeichnung im Browser - z.B. _ga für ein Google Analytics Cookie

#### dyn.

Hiermit bestimmen Sie ob es eine dynamische Variable ist - z.b. werden mit _g* alle Cokies geblockt die mit _g anfangen, also _ga, _gid usw.

#### Speichertyp

Wie werden die Daten in Ihrem Browser gespeichert.

#### Livetime / Expires

Wann läuft der Speichereintrag automatisch aus.

#### Wert

Welchen Wert transportiert das Cookie - in der Regel sind es kryptische Daten die hier gespeichert werden.

## Speichern

Mit Klick auf den Button Speichern werden die Daten in die CCM19 Administration Ihrer Seite übernommen und stehen dann direkt für das Frontend Widget zur Verfügung.Cookies der eigenen Seite manuell bestimmen



