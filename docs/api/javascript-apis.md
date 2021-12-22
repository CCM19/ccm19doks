# Javascript-APIs

CCM19 bietet mehrere Javascript-APIs, mit denen auf Funktionalitäten des Cookie-Managers zugegriffen und auf Benutzerinteraktionen reagiert werden kann.

## Globales Objekt

Die direkten Steuerungsmöglichkeiten von CCM19 sind im globalen Javascript-Objekt `CCM` gebündelt:

| Variable/Methode             | Typ      | Beschreibung                                                  |
| :--------------------------- | :------- | :------------------------------------------------------------ |
| CCM.version                  | string   | Enthält die aktuelle CCM19-Version. (ab Version 2020.10.28) |
| CCM.consent                  | boolean  | Gibt an, ob der Consent-Dialog geschlossen wurde.             |
| CCM.ucid                     | ?string  | Die eindeutige Consent-ID, oder null, wenn noch kein [Consent](https://www.ccm19.de/glossar/10-Consent.html#10) erteilt wurde. |
| CCM.acceptedCookies          | string[] | Liste der Namen aller akzeptierten [Cookies](https://www.ccm19.de/glossar/13-Cookies.html#13). |
| CCM.acceptedEmbeddings | [<br />  {<br />    _id_: `string`,<br />    _name_: `string`,<br />  }<br />  , …<br />] | Liste aller akzeptierten [Embeddings](https://docs.ccm19.de/funktionen/cookies-und-andere/). (ab Version 2020.10.28) |
| CCM.crossDomainConsentString | string   | Fragmentbezeichner zum manuellen Zusammensetzen einer URL für die [Consent-Teilung](../system-und-co/consent-speicherung.md#consent-teilung). (ab Version 2020.10.14) |
| CCM.openWidget()             |          | Öffnet den Cookie-Dialog erneut.                              |
| CCM.closeWidget()            |          | Schließt den Cookie-Dialog.                                   |
| CCM.openControlPanel()       |          | Öffnet den Dialog zur Auswahl der zu akzeptierenden Zwecke.   |
| CCM.closeControlPanel()      |          | Schließt den Dialog zur Auswahl der zu akzeptierenden Zwecke. |
| CCM.navigate(url\[, replace\[, navigateTop]]) |    | Navigiert zu einer anderen URL (wie `location.href = url`), berücksichtigt dabei aber die [Consent-Teilung](../system-und-co/consent-speicherung.md#consent-teilung). `replace` steuert, ob `location.replace` verwendet wird und `navigateTop` steuert, ob bei Frames die vollständige Seite navigiert wird. (ab Version 2020.10.14) |

Die Dialoge können alternativ auch über Links mit den Zielen `#CCM.openWidget`, `#CCM.closeWidget`, `#CCM.openControlPanel` und `#CCM.closeControlPanel` gesteuert werden.

## Javascript-Events

Einige Ereignisse in CCM19 werden zu CustomEvents auf dem `window`-Objekt abgebildet und mit `window.addEventListener(…)` kann darauf reagiert werden.

| Event               | detail-Eigenschaft                                           | Beschreibung                                                 |
| :------------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| ccm19WidgetClosed | null | Wird ausgelöst, sobald das letzte sichtbare CCM19-Widget-Element geschlossen wird. Dabei kann es sich um ein Resultat eines Klicks auf einen Speichern-Button handeln, der zum Schließen des Widgets führt. |
| ccm19WidgetLoaded   | null                                                         | Wird ausgelöst, sobald CCM19 fertig initialisiert wurde.     |
| ccm19CookieAccepted | {<br />  _name_: `string`,<br />  _code_: `string`,<br />  _purpose_: `string`,<br />  _mandatory_: `boolean`,<br />} | Ein Cookie wurde durch den Nutzer akzeptiert. Dieses Event wird für jedes Cookie ausgelöst, das in den akzeptierten Zwecken gelistet ist.Diese Events erfolgen beim Erteilen des Consents durch den Besucher und werden bei jeden folgenden Seitenbesuch beim Laden der Seite wiederholt.<br /><br />__Veraltet: Bitte auf `ccm19EmbeddingAccepted` umsteigen.__ |
| ccm19EmbeddingAccepted | {<br />  _name_: `string`,<br />  _code_: `string`,<br />  _purpose_: `string`,<br />  _mandatory_: `boolean`,<br />} | Ein Embedding wurde durch den Nutzer akzeptiert. Diese Events erfolgen beim Erteilen des Consents durch den Besucher und werden für jeden Seitenaufruf wiederholt.<br /><br />(ab Version 2020.10.28) |
