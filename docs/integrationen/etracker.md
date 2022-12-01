# eTracker richtig einrichten

Um zu ermöglichen, dass eTracker ohne Consent im Modus ohne Cookies arbeitet und nach Consent zusätzlich das Tracking mithilfe von Cookies aktiviert wird, muss unter "Einbindungen & Cookies" im Eintrag von eTracker im Feld "Quellcode der Einbindung" folgender Code hinterlegt werden:

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

Sollte der eTracker-Code nicht durch die Einbindung von CCM19 geblockt werden, sollte das obige Skript besser in eine technisch notwendige Einbindung verschoben werden, damit es immer ausgeführt wird, um auch ggf. die Funktion `_etracker.disableCookies` ausführen zu können. Hierfür bietet sich beispielsweise die technisch notwendige Einbindung des CCM19 selbst an.
