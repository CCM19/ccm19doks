# Consent Protokoll

Die Einwilligungen aller Besucher werden übersichtlich aufgelistet. Anhand einer ID sind Besucher eindeutig zu identifizieren, falls diese eine Auskunft über Ihre aktivierten Daten wünschen **und** Ihnen die eigene ID mitteilen. Ohne die Mitteilung bleiben diese Daten vollständig anonym da die ID eine Zufallszahl ist.

Die Protokollierung ist laut DSGVO Art 7, Abs. 1 zwingend vorgegeben. Selbstverständlich bleiben diese - wie auch alle anderen Daten - immer unter Ihrer Kontrolle und sind vollständig anonymisiert.

![screenshot-2020.12.17-13_46_18-1608209178770-1608211161873.jpg](../../assets/screenshot-2020.12.17-13_46_18-1608209178770-1608211161873.jpg)

In der Übersicht sehen Sie wie oft die jeweiligen Bereiche angehakt wurden. In der in diesem Beispiel verwendeten Maske wurden nur die beiden Bereiche Essentiell und Analyse angeboten - daher sind auch nur dort Haken zu verzeichnen.

## Export

Mit dem Button Export können Sie die Consent Daten des jeweiligen Monats per Klick auf den Button im .json Format exportieren. Ein Beispiel Eintrag sieht so aus - sie erkennen hier die ucid - mit der sich Ihre Besucher identifizieren können.

```
{
        "consent": true,
        "ucid": "387f1d311b2e7ba1f67722ac08bfdaf56aad3ecab6f11309d0c829f4e255af12",
        "timestamp": 1608208345,
        "purposes": {
            "41ba25c": "Technisch notwendig"
        },
        "embeddings": {
            "16bd7f0": "Papoo CMS Verwaltung der Session"
        },
        "manipulationPrevention": true
    }
```

## Consent Details

Für jeden Eintrag werden auch Consent Details gespeichert. Also ob in den einzelnen Kategorien auch einzelne Skripte / Einbindungen angehakt wurden.

![screenshot-2020.10.12-17_13_51-1602515631145.jpg](../../assets/screenshot-2020.10.12-17_13_51-1602515631145.jpg)

## Consent Protokoll nutzen bei Anfragen

Wenn Sie eine Anfrage bekommen bzgl. DSGVO ob Sie den Consent nachweisen können muss der Anfrager Ihnen seine ID mitteilen. Nach dieser können Sie mit der Suchmaske dann suchen.

Diese ID findet er in der Consent Maske an der folgenden Stelle. Dazu muss er die Consent Maske öffnen, auf Einstellungen klicken (falls noch nicht offen), dort dann auf das Fragezeichen neben einer der Kategorien.

![screenshot-2020.09.29-17_08_07-CCM19 - Cookie Consent Management Software.jpg](<../../assets/screenshot-2020.09.29-17_08_07-CCM19 - Cookie Consent Management Software.jpg>)

## Alternative Abfrage der ID

Alternativ kann die ID auch immer in den Entwicklerwerkzeugen entnommen werden wie auf dem Screenshot zu sehen ist. Die Daten finden Sie im Reiter Application - > dort links auf Local Storage und dann die eigene Domain auswählen.

![screenshot-2020.09.29-17_10_36-nimbus-capture.jpg](../../assets/screenshot-2020.09.29-17_10_36-nimbus-capture.jpg)

# Speicherdauer Consent

Da der Consent für 1 Jahr gespeichert wird, werden die Daten des Consents auch für diese Zeit gespeichert. Nach dem Ablauf dieses Jahres plus 1 Monat Karrenzzeit werden die Daten gelöscht. Somit sollte auch an dieser Stelle der DSGVO genüge getan sein.

## Protokoll archivieren

Hier können Sie alle bisherigen Protokolleinträge archivieren. Archivierte Einträge werden im Consent-Protokoll nicht mehr angezeigt, werden aber intern in komprimierter Form erhalten. Eine Archivierung erfolgt auch automatisch, sobald das Consent-Protokoll eine gewisse Größe überschreitet.

![screenshot-2020.12.17-13_47_04-1608209224291.jpg](../../assets/screenshot-2020.12.17-13_47_04-1608209224291.jpg)

### Statistiken zurücksetzen

Wenn ausgewählt, werden auch alle Statistiken über Einblendungen und akzeptierte Verwendungszwecke dieser Domain zurückgesetzt, sobald Sie das Protokoll archivieren. Die Daten werden also aus der Listung hier archiviert.
