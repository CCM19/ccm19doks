# Onboarding - Schritt 2

In diesem Schritt werden die Ergebnisse des automatischen Scans Ihrer Seite dargestellt. Hier können Sie die Daten übernehmen und anpassen. Für jeden gefundenen Anbieter resp. Einbettung wird ein Eintrag erstellt.

Zu jedem dieser Einträge werden die jeweils verwendeten Cookies und Storage Elemente aufgelistet.

## Scan Ergebnisse beurteilen

Für jeden Eintrag können Sie hier die rechtlich notwendigen Texte ergänzen und anpassen.

Im Hintergrund läuft eine Datenbank von CCM19 die abgefragt wird anhand der verwendeten Cookies und Storage Elemente.

Weiterhin wird ein Screenshot der Seite erstellt für Ihrer Kontrolle dass auch tatsächlich die korrekte Seite gescannt wurde.

![screenshot-1614090058662-662.jpg](../../assets/screenshot-1614090058662-662.jpg)

Die Ergebnisse teilen sich in die 5 Standard Kategorien auf in die Skripte, Cookies und Storage Elemente normalerweise zugeordnet werden.

- Technisch notwendig ( Essentiell)
- Anzeigen / Ads
- Analytics / Statistics
- Personalisierung
- Social Media
- Sonstiges

Hinter jedem Eintrag steht wie viele Einträge in der jeweiligen Kategorie gefunden wurden und automatisch zu sortiert werden konnten.

Für alle nach dem dafürhalten von CCM19 notwendigen Angaben werden Eingabefelder bereit gestellt.

### Name der Integration / Einbindung

Der Name der Einbindung - das kann z.B. Google Analytics sein oder Facebook Pixel. Hier sollten Sie einen aussagekräftigen Namen nutzen.

### Zweck

Hier tauchen wieder die schon oben genannten Kategorien auf. Sie können damit jeden Eintrag jeder beliebigen Kategorie zuweisen. Beachten Sie bitte aber dass Sie die rechtlichen Rahmenbedingungen beachten. Facebook Pixel z.B. wird sicher kaum unter technisch notwendig korrekt einsortiert sein.

### Aktivieren

Hiermit aktivieren Sie den Eintrag, so dass er auch im Frontend abgehakt werden kann

### Skripte blockieren.

Hier können Sie Skripte die im Quelltext Ihrer Seite eingebunden sind durch CCM19 blockieren. Nutzen Sie z.B. Google Analytics:

```
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

### Anbieter

Der Anbieter - hier muss der Firmenname des Anbieters rein der das Skript anbietet. In unserem Fall wäre es Google Ireland Limited. Tragen Sie hier auch gerne direkt die komplette Adresse des Unternehmens ein.

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

### Liste der Cookies und Storage Elemente

Hier sind alle Cookies und Storage Elemente aufgelistet die das Skript setzt. Sie können von Hand noch weitere Elemente eintragen, da der automatische Scan nicht immer alle Daten finden kann. Z.B. kann der Scanner keine Daten finden für einen eingeloggten Zustand.

### Name

Die Bezeichnung im Browser - z.B. \_ga für ein Google Analytics Cookie

### dyn.

Hiermit bestimmen Sie ob es eine dynamische Variable ist - z.b. werden mit \_g\* alle Cookies geblockt die mit \_g anfangen, also \_ga, \_gid usw.

### Speichertyp

Wie werden die Daten in Ihrem Browser gespeichert.

### Lifetime / Expires

Wann läuft der Speichereintrag automatisch aus.

### Wert

Welchen Wert transportiert das Cookie - in der Regel sind es kryptische Daten die hier gespeichert werden.

## Daten übernehmen

Wenn Sie alle Daten überprüft und notwendige Anpassungen durchgeführt haben, klicken Sie auf den Button unter dem Formular um die Daten in die CCM19 Administration zu übernehmen - siehe Screenshot.

![screenshot-2020.09.29-15_27_23-CCM19 Onboarding - Cookie Consent Management Software (1).jpg](<../../assets/screenshot-2020.09.29-15_27_23-CCM19 Onboarding - Cookie Consent Management Software (1).jpg>)
