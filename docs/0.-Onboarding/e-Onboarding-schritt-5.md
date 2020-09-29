# Onboarding - Schritt 5

Auf der letzten Seite des Onboardings finden Sie den Einbettungscode des CCM19 für Ihre Webseite. Den müssen Sie sich hier nicht merken - er wird genauso auch im Dashboard der Administration auch immer angezeigt.

![screenshot-2020.09.29-15_39_10-CCM19 Onboarding - Cookie Consent Management Software (3)](../assets/screenshot-2020.09.29-15_39_10-CCM19%20Onboarding%20-%20Cookie%20Consent%20Management%20Software%20(3).jpg)



## Einbindungscode

Der Einbindungscode kann z.B. so aussehen.

``` javascript
<script src="http://localhost/ccm19/cookie-consent-management/www/public/ccm19.js?apiKey=1234&amp;domain=1234&amp;lang=de_DE" 
referrerpolicy="origin">
    </script>
```



## Beispielintegration

Diesen Code kopieren Sie und binden in auf Ihrer Seite möglichst weit oben im Kopf der Seite ein, am besten direkt nach dem ersten <head> Element

``` html
<html>
 <head>
  <script src="http://CCM19ServerUrl/ccm19.js?apiKey=1234&domain=1234" 
          referrerpolicy="origin"></script>
 </head>
 <body>
 </body>
<html>    
```



## Fertig und raus

Wenn Sie fertig sind, klicken Sie auf den blauen Button und springen damit zurück in die CCM19 Administration.