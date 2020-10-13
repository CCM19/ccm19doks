# Consent Speicherung

CCM19 kann die Daten für den Consent sowohl in einem Cookie, im Local Storage oder auch im Session Storage speichern. Die einzelnen Methoden haben Vor und Nachteile.

![screenshot-2020.09.30-14_25_38-CCM19 - Cookie Consent Management Software (1)](../assets/screenshot-2020.09.30-14_25_38-CCM19%20-%20Cookie%20Consent%20Management%20Software%20(1).jpg)

## Speicherung als Cookie

Den Consent in einem Cookie zu speichern, erlaubt das Teilen des Consents über mehrere Subdomains und verschiedene Ports, aber kann die Seitenladezeit geringfügig verlängern. Das ist die klassische Speicherung der Daten.



## Speicherung im Local Storage

Den Consent im Local Storage zu speichern erlaubt es die Information in vielen Browsern unbegrenzt zu erhalten. Dabei wird der Consent aber auf eine Hostnamen-Port-Kombination beschränkt.



## Speicherung im Session Storage

Den Consent im Session Storage zu speichern, hält den Consent für jeden Browser-Tab getrennt. In dem Moment in dem der Tab geschlossen wird, wird auch der Consent vergessen.



# Eigenschaften und Consent Teilung

Über die Maske können Sie festlegen wie lange das CCM19 Cookie gespeichert werden soll. Standard sind 356 Tage = 1 Jahr ;-). Wenn Sie eine 0 eintragen wird das Cookie beim schließen des Browsers gelöscht.

Der Haken für "Sichere" Cookies kann nur gesetzt werden wenn kein ssl verwendet wird, dies ist aber heutzutage extrem selten.

![screenshot-2020.09.30-14_30_36-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-14_30_36-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



# Consent Teilung

Mit CCM19 ist es möglich den Consent unabhängig von Thirdparty Cookies über beliebig viele Domains und Subdomains hinweg zu teilen. Tragen Sie dazu die Liste der gewünschten Domains in das Feld ein.

> Diese Funktion steht nur in der Fullservice, Inhouse CMP und  Agency Variante zur Verfügung.

Für jede eingetragene Domain kann der Consent zwischen den Subdomains der eingegebenen Domain geteilt werden, solange das selbe Code-Snippet verwendet wird. Geben Sie z.B. <code>example.com</code> ein, damit nur einmal Consent für example.com, www.example.com und alle anderen Subdomains, die auf .example.com enden, erteilt werden muss. Ungültige Eingaben können dazu führen, dass das Speichern des Consents nur noch unzuverlässig funktioniert

Der Consent wird über HTML Links, Iframes und über Javscript generierte Links weitergeben. 

## Consent Teilung im iframe

Falls Sie eine Webseite haben wo ein iframe einer anderen ihrer Seiten eingesetzt wird, z.B. eine Buchungsmaske erscheint dann in dem iframe nicht nochmal eine Abfrage, sondern der Consent wird übertragen. Dies funktioniert natürlich nur wenn sie oben eingetragen sind und somit auch die gleichen Skripte und Cookies teilen.