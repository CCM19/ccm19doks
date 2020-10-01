# Kunden API

Informationen zu Ihrer Kunden API finden Sie im Admin Dashboard unter dem Menüpunkt Kunden-API. Mit Hilfe der Kunden API können Sie folgende Aktionen durchführen.

* Kunden erstellen
* Kundendaten auslesen
* Kundendaten bearbeiten / aktualisieren
* Kunde löschen

Natürlich können alle diese Aktionen nur durchgeführt werden wenn eine entsprechende Autorisierung vorliegt.

## Verbindung zur API herstellen

Um eine API-Anfrage erfolgreich zu verarbeiten, hängen Sie den API-Schlüssel an **jede Anfrage** an, indem Sie den GET-Parameter `apiKey` hinzufügen und den Schlüssel als Wert festlegen.

Setzen Sie für jede POST- und PUT-Anfrage den HTTP-Header `Content-Type` auf `application/json`; d.h. für jede Anfrage, die einen Nachrichtenkörper enthält. Kodieren Sie den zu sendenden Payload entsprechend.

![screenshot-2020.10.01-13_53_19-1601553199653](../assets/screenshot-2020.10.01-13_53_19-1601553199653.jpg)

Die echten API Schlüssel sind natürlich wesentlich komplexer ;-) 

> **Halten Sie Ihren API-Schlüssel immer geheim. Wenn der Schlüssel kompromittiert ist, können Sie ihn hier ändern; danach müssen Sie all Ihre Apps aktualisieren.**