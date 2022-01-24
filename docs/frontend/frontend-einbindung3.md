# Integration Typ 3 - Beispiel Google Adsense

Sie können CCM19 auch nutzen um im Quelltext blockierte Skripte via Consent freizugeben und ausführen zu lassen.

Um dies zu nutzen, können Sie Ihren Skripten unseren CCM19-spezifischen Wert für das `type`-Attribut vergeben. Durch diese Anpassung erkennt ein Browser das entsprechende Skript nun nicht mehr als auszuführenden Javascript-Code und lässt von der Verarbeitung dessen zunächst ab.

Wie Sie das `type` Attribut in Ihre Website verändern, werden wir hier chronologisch anhand eines Beispiels erklären. Im Beispiel richten wir **Google Adsense** für eine Website ein und nehmen entsprechende Konfigurationen am Skript vor, damit alles gemäß der DSGVO, dem TTDSG und den Vorgaben des IAB und denen von Google konfiguriert wird.

### 1. Skript lokalisieren

Zuerst müssen wir alle Skripte auf **Ihrer** **Website** finden. Häufig werden Skripte im <head> der Website platziert, da dieser auf jeder Seite der Domain geladen wird. Bei Google Adsense erhält man jedoch neben dem allgemeinen Skript, auch weitere, die mit den individuellen Anzeigen eingebunden werden.

Hier sehen wir das Skript zur Einbindung im <head> der Seite:

```
<script data-ad-client="ca-pub-XXXXXXXXXXXXXXX" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
```

Und hier wäre ein Beispiel für eine horizontale Anzeige, die an einem festen Ort auf der Seite platziert wird:

```javascript
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXX"
     crossorigin="anonymous"></script>
<!-- Horizontale Anzeige Test -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXX"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
```

### 2. Skript-Typ hinzufügen

Wenn nun alle Skripte gefunden wurden, die wir unter die Kontrolle von CCM19 bringen wollen, können wir folgenden Teil hinzufügen:

```
type="text/x-ccm-loader"
```

Ergänzen Sie das `type`-Attribut wie folgt oder aktualisieren den Wert, falls das Attribut bereits vorhanden ist. Das Attribut wird im öffnenden `script`-Tag (innerhalb der spitzen Klammern `<>`) definiert.

Durch diese Anpassung verhindert man effektiv dass die Resource / das Skript vom Browser ohne Consent geladen wird. Erst mit der Erteilung des Consents werden die Skripte dann geladen / aktiviert.

```
<script data-ad-client="ca-pub-XXXXXXXXXXXXXX" 
        async 
        src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js" 
        type="text/x-ccm-loader"
></script>
```

Die Zeilenumbrüche sind nur zur simpleren Veranschaulichung, es kann auch alles in einer Zeile stehen. Achten Sie dabei darauf, dass alle Attribute durch ein Leerzeichen getrennt sind.

Da wir ja auch weitere Skripte haben, müssen nun alle anderen ebenfalls bearbeitet werden. In unserem Beispiel betrifft das noch die horizontale Anzeige:

```
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXX"
     crossorigin="anonymous" type="text/x-ccm-loader" ></script>
<!-- Horizontale Anzeige Test -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXX"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script type="text/x-ccm-loader">
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
```

### 3. Gruppenname hinzufügen

Damit die Skripte nun auch zusammen freigeschaltet werden können bzw. durch den Consent der Besucher aktiviert werden können, fügen wir den Skripten ein weiteres Attribut hinzu:

```
data-ccm-loader-group="adsbygoogle"
```

Dabei ist der Ausdruck in den Anführungszeichen frei wählbar. Hier haben wir uns für "adsbygoogle" entschieden.

Nun fügen wir diesen Teil noch den bereits bearbeiteten Skripten hinter dem Type-Attribut hinzu:

```
<script data-ad-client="ca-pub-XXXXXXXXXXXXXX" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js" type="text/x-ccm-loader" data-ccm-loader-group="adsbygoogle"></script>
```

Und auch wider in der horizontalen Anzeige:

```
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXX"
     crossorigin="anonymous" type="text/x-ccm-loader" data-ccm-loader-group="adsbygoogle"></script>
<!-- Horizontale Anzeige Test -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXX"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script type="text/x-ccm-loader" data-ccm-loader-group="adsbygoogle">
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
```

### 4. Gruppierung in CCM19 definieren

Aktuell hat die letzte Maßnahme noch keinen Effekt, da CCM19 die Gruppierung nicht kennt. Navigieren wir also in der administrativen Oberfläche von CCM19 zum entsprechenden Embedding und bearbeiten wir es:

\####Bild von Embedding-Übersicht####

Hier sehen wir recht weit oben ein Feld, um Gruppennamen einzutragen. Dort tragen wir unser selbst definierten Gruppennamen ein. In unserem Fall lautet er "adsbygoogle".

\####Bild aus den Einstellungen####

Vergessen Sie nicht zu speichern!