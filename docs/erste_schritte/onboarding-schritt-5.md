# Onboarding - Schritt 5

Auf der letzten Seite des Onboardings finden Sie den Einbettungscode des CCM19 für Ihre Webseite. Den müssen Sie sich hier nicht merken - er wird genauso auch im Dashboard der Administration auch immer angezeigt. Sie können ihn aber natürlich direkt kopieren und in Ihre Seite einbinden.

![screenshot-1614090586768-768.jpg](../../assets/screenshot-1614090586768-768.jpg)

## Einbindungscode

Der Einbindungscode kann z.B. so aussehen.

```
<script src="http://localhost/ccm19/cookie-consent-management/www/public/ccm19.js?apiKey=1234&amp;domain=1234&amp;lang=de_DE" 
referrerpolicy="origin">
    </script>
```

## Beispielintegration

Diesen Code kopieren Sie und binden in auf Ihrer Seite möglichst weit oben im Kopf der Seite ein, am besten direkt nach dem ersten Element

```
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
