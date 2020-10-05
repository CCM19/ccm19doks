# Agency Version

Die Agency Version verfügt über einige spezielle Features, die speziell Agenturen oder andere Wiederverkäufer optimal nutzen können.

Zusätzlich kann die Agency Version auch als komplette Whitelabel Version umgesetzt werden, wo sowohl das Frontend wie auch das Backend komplett individualisiert sind und alle Hinweise auf CCM19 entfernt sind.

Mit der Agency Version haben Sie auch die Möglichkeit das CCM19 an Ihre Kundenverwaltung anzuschließen oder per API neue Kunden zu erstellen und zu bearbeiten.

## Installation Agency Version

Die Installation der Agency Version erfolgt genauso wie die Downloadvariante - der Prozess ist der gleiche. Sie bekommen nur eine spezielle Downloaddatei und einen speziellen Lizenzkey der die Nutzung ermöglicht.


## Installationsdatei herunterladen

Die Installationsdatei bekommen Sie entweder per Mail oder WeTransfer zugesendet oder Sie finden sie im Downloadbereich von CCM19.de - nach Abschluß als Reseller bekommen Sie eine E-Mail wo genau steht wo Sie die Dateien finden. 

Die Maske sieht dabei folgendermaßen aus. Unter dem Reiter Lizenzen finden Sie den Lizenkey den Sie im Schritt 2 der Installation brauchen. Die Keys können auch zurückgesetzt werden.

![screenshot-2020.09.30-11_13_10-Account _ Download Version Login](../assets/screenshot-2020.09.30-11_13_10-Account%20_%20Download%20Version%20Login.jpg)

## Dateien entpacken und hochladen

Nach dem Download der Dateien erhalten Sie eine .zip Datei. Diese Datei müssen Sie auf Ihrem PC entpacken.  Auf Ihrem Rechner werden nun zwei neue Datein abgelegt. *setup.php* und *ccm19.zip*.



## Dateien per FTP auf Ihren Server hochladen

Nach dem Entpacken müssen Sie Ihre Dateien per FTP / SSH oder andere Wege auf Ihren Server spielen. Es empfiehlt sich, den Anweisungen des Hosters zu folgen. 

Die Dateien *setup.php* und *ccm19.zip* laden Sie in das Stamm-Verzeichnis Ihrer Webseite (oder einen beliebig erstellten Ordner).

CCM19 erstellt standardmäßig einen Unterordner /ccm19. Legen Sie also Ihre Datein entsprechend Ihrer Wünsche ab. Wenn Sie CCM19 in das aktuelle Verzeichnis statt einen Unterordner installieren möchten, tragen Sie bitte `./` in die Maske für das Verzeichnis ein.



## PHP Version beachten

Die verwendete PHP Version muss mindestens **PHP 7.2.x** lauten – oder höher. Falls Sie auf Ihrer Seite die PHP-Version nicht ohne Weiteres updaten können, besteht die Alternative, dass Sie bei Ihrem Provider eine (Sub-)Domain einrichten und dort die PHP Version auf 7.2 oder höher stellen. 

Sie können das CCM19 Skript dann auf dieser (Sub-)Domain installieren und von dort aus in Ihre eigentliche Seite einbinden.

Falls auch das nicht funktioniert oder Ihnen der Aufwand zu hoch ist, steht Ihnen die [Service Variante](https://www.ccm19.de/ccm19-service-tarife.html) unseres Tools zur Verfügung – hier muss nichts installiert werden.

  

## Installation - Schritt 1

Navigieren Sie auf Ihrer Webseite nun zu dem Ordner, in dem Sie die Dateien abgelegt haben und rufen darin die Datei *setup.php* auf. In unserem Beispiel wäre dies https://www.MeineDomain.de/setup.php, da wir die Dateien direkt im Stammverzeichnis abgelegt haben.

![screenshot-2020.10.01-10_50_39](../assets/screenshot-2020.10.01-10_50_39.jpg)



**Das CCM19-Tool wird in diesem Beispiel später über https://www.MeineDomain.de/ccm19/ erreichbar sein.**

In diesem Screen können Sie das Installationsverzeichnis ändern. Hier können Sie auch Ordner wie /cookies/, /kekse/ oder ähnliches, aber auch ./ für das aktuelle Verzeichnis angeben. Für unser Beispiel belassen wir es bei /ccm19/.

### Schreibrechte

Bitte achten Sie darauf dass Sie die Schreibrechte für das Verzeichnis korrekt setzen damit das Setup Skript die Dateien dort hineinschreiben kann, ansonsten kommt es zu der folgenden Fehlermeldung.



![screenshot-2020.10.01-10_49_49](../assets/screenshot-2020.10.01-10_49_49.jpg)



## nginx? - Serverkonfiguration anpassen

Sofern Sie **nginx** als Webserver verwenden, sind üblicherweise Anpassungen an der Serverkonfiguration nötig. Falls Sie nginx verwenden - ist eine Anpassung der Serverkonfiguration notwendig. Mehr Informationen dazu finden Sie im Technikbereich:  [Technik](../api/technik.md) 



## Schritt 2 - Lizenzkey eintragen

![screenshot-2020.10.01-10_52_37](../assets/screenshot-2020.10.01-10_52_37.jpg)

Nach der kurzen Installation werden Sie auf die Registrierungsmaske weitergeleitet. Hier müssen Sie Ihren gekauften Lizenzschlüssel eingeben, den Sie [hier](https://www.ccm19.de/account.php?menuid=248&account_extuser=4) einsehen können.

![screenshot-2020.10.01-10_41_35](../assets/screenshot-2020.10.01-10_41_35.jpg)

Oder Sie navigieren auf der ccm19.de Seite im Top-Menu unter **Login** > **Download Version Login** und danach im **Sub-Menu** zum Punkt **Lizenzen**. Dort kopieren Sie Ihren Lizenzschlüssel und fügen ihn in die entsprechende Spalte ein.

Danach tragen Sie noch eine gültige E-Mail Adresse ein (ohne gültige E-Mail Adresse können Sie später Ihr Passwort nicht zurücksetzen!). Danach können Sie noch einen Usernamen und ein Passwort wählen. **Der Benutzername kann später NICHT mehr geändert werden!** Klicken Sie danach auf "Setup durchführen" und das System wird installiert.

Weiterhin können Sie unter "Erweiterte Einstellungen" einen Proxy Server angeben falls in Ihrem Unternehmen einer benutzt wird für die Ausgabe der Webseite - dies ist aber ein sehr seltener Zustand. In der Regel wird dies nicht gemacht.

> Beachten Sie bitte das der Benutzername / Benutzer den Sie bei der Installation erstellen auch der spätere Administratoraccount ist.
> 



## Fertig

Sobald das Installationskript fertig ist, werden Sie zur [Loginmaske](login-und-passwoerter.md) weitergeleitet oder direkt eingeloggt und Sie landen im Dashboard.



## Etwas klappt nicht?

Dann fragen Sie unseren Support unter 0228 / 280 5668 oder einfach per E-Mail an [info@ccm19.de](mailto:info@ccm19.de). 



## Nach der Installation

Im Anschluß an die Installation sollten Sie noch die Setup Dateien löschen damit das Setup nicht erneut durchgeführt werden kann - Sie bekommen dazu auch einen entsprechenden Hinweis in der Administration.

![screenshot-2020.10.01-10_56_01](../assets/screenshot-2020.10.01-10_56_01.jpg)



### Key zurücksetzen

Mit dem Button zurücksetzen können Sie der Installation jederzeit den Key entziehen und neu setzen. Das macht z.B. Sinn wenn Sie die Installation erst auf einer Subdomain testen und dann später im Livesystem erneut installieren.



## Erster Login - Agency Dashboard

Das Agency Dashboard bietet einige Basisinformationen über die Nutzung der Agency Version. Zum einem wieviel Kunden in der Datenbank vorliegen und wieviele Domains darüber genutzt werden.

Außerdem sehen Sie eine kleine Grafik die die Auslastung Ihrer CCM19 Instanz zeigt.



![screenshot-2020.10.01-12_09_01](../assets/screenshot-2020.10.01-12_09_01.jpg)

 Weitere Informationen finden Sie links im Menü.