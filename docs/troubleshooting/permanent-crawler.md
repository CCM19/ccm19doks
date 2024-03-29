# Was mache ich mit den Ergebnissen des Permanent Crawlers?

Trotz korrekter Konfiguration und Abschluss des Quicksetups kann es vereinzelt zu Einträgen im Permanent Crawler kommen. Diese weisen Sie darauf hin, dass kritische Inhalte immer noch geladen werden. Dabei kann es sich um Cookies, Local Storage Elemente, Skripte oder sonstige Inhalte handeln. Um Ihre Seite also fortlaufend zu schützen, sollten alle Einträge von Ihnen überprüft werden. Wie Sie dabei bestmöglich vorgehen, erklären wir hier.

## 1. Werden die Elemente wirklich von meiner Website geladen?

Da unser Scann clientseitig funktioniert, kann esmitunter vorkommen, dass Elemente des Nutzers bereits vor dem Betreten Ihrer Seite im Browser geladen sind. Dies können Cookies sein, die der Nutzer von anderen Seiten mitschleppt, oder individuelle Konfigurationen durch beispielsweise ein Addon im Browser. Daher empfielt es sich kurz über das Cookie, das Local Storage Element oder das Skript zu informieren. In der Regel reicht eine kleine Suche mit einer Suchmaschine, um mehr Informationen zu erhalten. Der Permanent Crawler weist auch genaue URLs aus, auf denen die Elemente gefunden wurden. Dies hilft einem bei der Kontrolle der eigenen Seite.

## 2. Entsprechend Handeln

### 2.1 Ich setze dieses Cookie oder dessen Anbieter nicht bei mir ein

Sollten Sie feststellen, dass die aufgelisteten Elemente nicht von Ihrer Seite kommen können, reicht ein Klick auf den Button "Ignorieren". Diese Einträge führen zukünftig also nicht mehr zu einer Warnmeldung und werden nicht erneut aufgelistet. Ignorierte Einträge können nachträglich wieder gelöscht werden, um die Einstellung rückgängig zu machen.

### 2.2 Meine Seite nutzt dieses Cookie und seinen Anbieter

Stellen Sie fest, dass dieser Anbieter vergessen wurde, können Sie auf den Button "Übernehmen" klicken. Sie wechseln anschließend zum Menüpunkt "Einbindung & Cookies" und können das Cookie einem bestehenden Anbieter hinzufügen, einem neuen Anbieter hinzufügen oder einem Anbieter aus der Datenbank hinzufügen.

Skripte lassen sich so nicht importieren. Sobald Sie herausgefunden haben, um welchen Anbieter es sich handelt, erstellen Sie einfach einen Eintrag oder öffnen Sie einen vorhanden Eintrag und fügen Sie einen eindeutigen Teil des Skripts in das Feld "Skripte blockieren die folgenden Text enthalten" hinzu. Mehr zu dieser Funktion finden Sie [hier](https://docs.ccm19.de/funktionen/cookies-und-andere/#skripte-blockieren).
