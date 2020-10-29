# Google Tag Manager

Da der Tag Manager als Container fungiert, über den Skripte in die Webseite eingebunden werden können, tauchen die Skripte nicht direkt im Quellcode auf. Entsprechend ist es nie möglich, die Skripte aus der Seite zu entfernen und beim Cookie neu einzubinden.

Um Skripte, die über den Tag Manager geladen werden, zu blocken, wird idealerweise ausschließlich das Feature "Embeddings blockieren, die folgenden Text enthalten" verwendet. Damit das Blocken der Skripte funktioniert, muss aber sichergestellt werden, dass der CCM19-Code im Quelltext vor dem Tag-Manager-Code steht.



## Integration in Google Tag Manager

Über die Schnittstelle `window.dataLayer` werden Events im Google Tag Manager ausgelöst, falls dieser auf der Zielseite eingebunden ist.

Sobald ein Embedding über die CCM19-Oberfläche zugelassen wird, wird folgendes Event ausgelöst. Die Events werden bei jedem Seitenaufruf für alle zugelassenen Embeddings wiederholt abgefeuert.

```javascript
window.dataLayer.push({
    event: 'CCM19.embeddingAccepted', // Konstanter Bezeichner
    id: 'xxxxxxx', // CCM19-interne Embedding-ID
    name: 'Google Analytics', // Benutzerdefinierter Embedding-Name
});
```

Im Tag Manager kann über Triggers → New → Custom Events darauf reagiert werden.

### Cookiebasiert (veraltet)

> __Veraltet:__ Bitte nicht für neue Projekte verwenden; alten Code auf Embedding-Events umstellen.

Über den DataLayer wird im Google Tag Manager für jedes Cookie, das erlaubt wird, ein „Custom Event" ausgelöst:

```
CCM19.cookieAccepted.<cookiename>
```

Also z.B. `CCM19.cookieAccepted._ga` für das Cookie **_ga**.





Work in Progress...