# Netzwerk / Proxy Einstellungen

Diese speziellen Einstellungen kommen nur sehr selten zum Einsatz. CCM19 ist so aufgebaut dass es in der Regel mit den normalen Einstellungen der Provider problemlos zurecht kommt.

![screenshot-2020.09.30-14_53_58-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-14_53_58-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

## HTTPS-Verbindung erzwingen

Verwenden Sie diese Option, wenn sich die Anwendung hinter einem Load-Balancer oder ähnlicher Umgebung befindet, in der z.B. SSL-Offloading stattfindet. Wenn bestimmte Header nicht weitergeleitet werden, wird eine HTTPS-Verbindung u.U. nicht automatisch erkannt, weshalb Frontend-Ressourcen fälschlicherweise über eine ungesicherte Verbindung angefordert werden können. 

Bei Problemen mit SSL Funktionen ist das also Ihre erste Anlaufstelle.



## Proxy Einstellungen

Verwenden Sie diese Option **nur**, wenn Verbindungen von diesem Server aus durch einen firmeneigenen Proxy geleitet werden müssen. Nutzen Sie `*server*:*port*` oder `http://*server*:*port*` für HTTP-Proxies, `https://*server*:*port*` für HTTPS-, `socks4://*server*:*port*` für SOCKS 4- und `socks5://*server*:*port*` für SOCKS 5-Proxies.



![screenshot-2020.09.30-14_55_36-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-14_55_36-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)