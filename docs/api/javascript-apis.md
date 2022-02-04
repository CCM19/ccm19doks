# Javascript APIs

CCM19 provides several Javascript APIs that can be used to access Cookie Manager functionality and respond to user interactions.

## Global object

The direct control capabilities of CCM19 are bundled in the global javascript object `CCM`:

| Variable/Method | Type | Description |
| :--------------------------- | :------- | :------------------------------------------------------------ |
| CCM.version | string | Contains the current CCM19 version. (as of version 2020.10.28) |
| CCM.consent | boolean | Indicates whether the consent dialog was closed.             |
| CCM.ucid | ?string | The unique Consent ID, or null if no [Consent](https://www.ccm19.de/glossar/10-Consent.html#10) has been granted yet. |
| CCM.acceptedCookies | string[] | List of names of all accepted [Cookies](https://www.ccm19.de/glossar/13-Cookies.html#13). |
| CCM.acceptedEmbeddings | [<br /> {<br /> _id_: `string`,<br /> _name_: `string`,<br /> }<br />, ...<br />] | List of all accepted [Embeddings](https://docs.ccm19.de/funktionen/cookies-und-andere/). (as of version 2020.10.28) |
| CCM.crossDomainConsentString | string | fragment identifier to manually compose a URL for [consent-sharing](../system-and-co/consent-storage.md#consent-sharing). (as of version 2020.10.14) |
| CCM.openWidget() | Reopens the cookie dialog.                              |
| CCM.closeWidget() | | Closes the cookie dialog.                                   |
| CCM.openControlPanel() | | Opens the dialog for selecting the purposes to accept.   |
| CCM.closeControlPanel() | | Closes the dialog for selecting the purposes to accept. |
| CCM.navigate(url\[, replace\[, navigateTop]]) | | Navigates to another URL (like `location.href = url`), but takes into account the [consent-sharing](../system-and-co/consent-storage.md#consent-sharing). `replace` controls whether `location.replace` is used and `navigateTop` controls whether the full page is navigated for frames. (as of version 2020.10.14) |

The dialogs can alternatively be controlled by links with the targets `#CCM.openWidget`, `#CCM.closeWidget`, `#CCM.openControlPanel` and `#CCM.closeControlPanel`.

## Javascript events

Some events in CCM19 are mapped to CustomEvents on the `window` object and `window.addEventListener(...)` can be used to react to them.

| Event | detail property | Description |
| :------------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| ccm19WidgetClosed | null | Fired when the last visible CCM19 widget element is closed. This can be a result of a click on a save button which leads to closing the widget. |
| ccm19WidgetLoaded | null | Will be triggered as soon as CCM19 has finished initializing.     |
| ccm19CookieAccepted | {<br /> _name_: `string`,<br /> _code_: `string`,<br /> _purpose_: `string`,<br /> _mandatory_: `boolean`,<br />} | A cookie was accepted by the user. This event is triggered for each cookie listed in the accepted purposes.These events occur when the visitor gives consent and are repeated on each subsequent page visit when the page is loaded. <br /><br /> __Veraltet: Please change to `ccm19EmbeddingAccepted` __ |
| ccm19EmbeddingAccepted | {<br /> _name_: `string`,<br /> _code_: `string`,<br /> _purpose_: `string`,<br /> _mandatory_: `boolean`,<br />} | An embedding was accepted by the user. These events occur when the visitor consents and are repeated for each page load. <br /><br /> (as of version 2020.10.28) |
