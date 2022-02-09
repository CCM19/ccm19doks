# **Youtube-Videos und andere Iframes werden auf meiner Seite nicht blockiert**

Youtube-Videos werden nicht automatisch blockiert, sondern erfordern den Einsatz unserer Iframe-Blockers. Dieser kann unter dem Menüpunkt „Iframes“ aktiviert werden.

Sollten auch bei aktiviertem Iframe-Blocker Elemente nicht blockiert werden, hat dies vor allem zwei Ursachen:

1\. Der Code des CCM19 steht im Quellcode hinter dem Iframe, so dass dieser bereits geladen wurde, bevor CCM19 eine Gelegenheit hatte, ihn zu blockieren. Stellen Sie sicher, dass das CCM19-Code-Snippet möglichst weit oben im <head> der Seite und somit vor allen Iframe-Inhalten eingebunden ist.

2\. Das Objekt, das blockiert werden soll, ist gar kein Iframe. Google Maps beispielsweise kann als Iframe oder als Div-Container eingebunden werden. Optisch unterscheiden sich die beiden Einbindungen bisweilen kaum voneinander. Überprüfen Sie also, ob das Objekt, das Sie blockieren möchten, wirklich ein Iframe ist. Auch Video-Anbieter stellen immer häufiger Optionen für eine Einbindung ohne Iframes zur Verfügung.