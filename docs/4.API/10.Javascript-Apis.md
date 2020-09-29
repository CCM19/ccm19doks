# Javascript-APIs

CCM19 bietet mehrere Javascript-APIs, mit denen auf Funktionalitäten des Cookie-Managers zugegriffen und auf Benutzerinteraktionen reagiert werden kann.

## Globales Objekt

Die direkten Steuerungsmöglichkeiten von CCM19 sind im globalen Javascript-Objekt `CCM` gebündelt:

| Variable/Methode        | Typ      | Beschreibung                                                 |
| :---------------------- | :------- | :----------------------------------------------------------- |
| CCM.consent             | boolean  | Gibt an, ob der Consent-Dialog geschlossen wurde.            |
| CCM.ucid                | ?string  | Die eindeutige Consent-ID, oder null, wenn noch kein [Consent](https://www.ccm19.de/glossar/10-Consent.html#10) erteilt wurde. |
| CCM.acceptedCookies     | string[] | Liste der Namen aller akzeptierten [Cookies.](https://www.ccm19.de/glossar/13-Cookies.html#13) |
| CCM.openWidget()        |          | Öffnet den Cookie-Dialog erneut.                             |
| CCM.closeWidget()       |          | Schließt den Cookie-Dialog.                                  |
| CCM.openControlPanel()  |          | Öffnet den Dialog zur Auswahl der zu akzeptierenden Zwecke.  |
| CCM.closeControlPanel() |          | Schließt den Dialog zur Auswahl der zu akzeptierenden Zwecke. |

Die Dialoge können alternativ auch über Links mit den Zielen `#CCM.openWidget`, `#CCM.closeWidget`, `#CCM.openControlPanel` und `#CCM.closeControlPanel` gesteuert werden.

## Javascript-Events

Einige Ereignisse in CCM19 werden zu CustomEvents auf dem `window`-Objekt abgebildet und mit `window.addEventListener(…)` kann darauf reagiert werden.

| Event               | detail-Eigenschaft                                           | Beschreibung                                                 |
| :------------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| ccm19WidgetLoaded   | null                                                         | Wird ausgelöst, sobald CCM19 fertig initialisiert wurde.     |
| ccm19CookieAccepted | { "name": string, "code": string, "purpose": string, "mandatory": boolean } | Ein Cookie wurde durch den Nutzer akzeptiert. Dieses Event wird für jedes Cookie ausgelöst, das in den akzeptierten Zwecken gelistet ist.Diese Events erfolgen beim Erteilen des Consents durch den Besucher und werden bei jeden folgenden Seitenbesuch beim Laden der Seite wiederholt. |

## Google Tag Manager Events

Über den DataLayer wird im Google Tag Manager für jedes Cookie, das erlaubt wird, ein „Custom Event" ausgelöst:

```
CCM19.cookieAccepted.<cookiename>
```

Also z.B. `CCM19.cookieAccepted._ga` für das Cookie **_ga**.

Im Tag Manager kann über Triggers → New → Custom Events darauf reagiert werden.