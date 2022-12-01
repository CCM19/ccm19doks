# eTracker richtig einrichten

eTracker bietet die Möglichkeit des Trackings ohne das Setzen von Cookies an. Diese Art des Trackings ist dadurch auch ohne Zustimmung des Webseitenbesuchers möglich und kann auch aktiv bleiben, wenn alle Cookies abgelehnt wurden. Beim Tracking ohne Cookies können allerdings nicht mehr im gewohnten Maß Daten erfasst werden, so dass idealerweise nach Consent des Users in den Tracking-Modus gewechselt wird, bei dem Cookies gesetzt werden.

Um das zu ermöglichen, muss CCM19 die Information, dass der Webseitenbesucher der Nutzung von eTracker-Cookies zugestimmt hat, an eTracker übermitteln. Um das zu ermöglichen, muss in einer technisch notwendigen Einbindung (beispielsweise die Einbindung von CCM19 selbst, die immer vorhanden ist und ausgeführt wird) unter "Einbindungen & Cookies" im Feld "Quellcode der Einbindung" folgender Code hinterlegt werden:

```html
<script defer>
    (function () {
        var intervals = {};

        function updateEtracker() {
            if (typeof window._etracker == 'object'
                && typeof _etracker.enableCookies == 'function'
                && typeof _etracker.disableCookies == 'function'
            ) {
                CCM.acceptedEmbeddings.reduce(function (c,i) { return c || i.name == 'eTracker'; }, false)
                    ? _etracker.enableCookies(window.location.host)
                    : _etracker.disableCookies(window.location.host);
                window.clearInterval(intervals.etracker);
                intervals.etracker = null;
            }
        }

        function updateThirdPartyConsentState() {
            if (intervals.etracker) {
                window.clearInterval(intervals.etracker);
            }
            intervals.etracker = window.setInterval(updateEtracker, 200);
        }

        window.addEventListener('ccm19WidgetClosed', updateThirdPartyConsentState);
        updateThirdPartyConsentState();
    })();
</script>
```

Wichtig ist hierbei, dass der Name der Variable in `i.name == 'eTracker'` immer mit dem Namen der eTracker-Einbindung in CCM19 übereinstimmt. Wenn die Einbindung "eTracker" heißt, muss also nichts geändert werden.
