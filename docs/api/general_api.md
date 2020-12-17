# Domain API / General API

Mit der domainspezifischen API können Sie Consent und Ereignisdaten pro Domain und über eine gesicherte SSL Schnittstelle in andere Systeme integrieren.

Der Aufruf erfolgt generell mit Ihrem Api Key - ohne diesen ist der Aufruf nicht erfolgreich. Jeder Key ist immer nur für einen Account valide.

Der Aufruf erfolgt generell per simplen GET Aufruf im Browser, curl oder eine beliebige andere Möglichkeit Webdaten aufzurufen.

## API testen

Sie können einen Testaufruf durchführen. Rufen Sie dafür folgende url auf:

```url
https://ihre_ccm19_instanz/api/test?apikey=IHR_API_KEY
```

Darauf sollte das System folgendermaßen antworten.

```json
{
    "username": "Ihr_Username",
    "apiKey": "IHR_API_KEY"
}
```

## Alle Domains des Accounts listen

Um alle Domains Ihres Accounts zu listen rufen Sie bitte folgende URL auf.

```url
https://ihre_ccm19_instanz/api/getdomains?apikey=IHR_API_KEY
```

Die Antwort sollte folgendermaßen lauten

```json
{
    "b61cd4a": {
        "domainId": "b61cd4a",
        "domainName": "https:\/\/www.test-xy.de",
        "domainWhiteLabel": false,
        "domainViewCount": 0
    },
    "1ed845d": {
        "domainId": "1ed845d",
        "domainName": "test-12.de",
        "domainWhiteLabel": false,
        "domainViewCount": 0
    }
}
```

Die domId ist die wichtigste Information - damit können Sie weitere Informationen zur Domain holen.

## Alle Consents des aktuellen Monats holen

Mit dem folgenden Aufruf holen Sie alle Consents des aktuellen Monats. Bitte ersetzen Sie in der url DOM_ID mit einer domId aus der obigen Abfrage.

```url
https://ihre_ccm19_instanz/api/domain/consents?apikey=IHR_API_KEY&domainId=DOM_ID
```

Die Antwort lautet wie folgt:

```json
[
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
    },
    {
        "consent": true,
        "ucid": "387f1d311b2e7ba1f67722ac08bfdaf56aad3ecab6f11309d0c829f4e255af12",
        "timestamp": 1608208338,
        "purposes": {
            "41ba25c": "Technisch notwendig"
        },
        "embeddings": {
            "16bd7f0": "Papoo CMS Verwaltung der Session"
        },
        "manipulationPrevention": true
    },
    {
        "consent": true,
        "ucid": "cba4803da92a9b39ffa82cc93aecbe00bc3f695530ebd3f7e67326404073bdbd",
        "timestamp": 1608131136,
        "purposes": {
            "41ba25c": "Technisch notwendig"
        },
        "embeddings": {
            "16bd7f0": "Papoo CMS Verwaltung der Session"
        },
        "manipulationPrevention": true
    }
]
```

Aufgelistet werden die Consents folgendermaßen:

* consent: true / false - wurde ein Consent erteilt
* ucid: eine individuelle Consent ID eines Besuchers
* timestamp: Zeitstempel des Consentes
* purposes: Welche Kategorie der Consent angehört
* embeddings: Welchen Einbettungen resp. Cookies der Besucher zugestimmt hat
* manipulationPrevention: true / false - ob Versuche zur Manipulation unterbunden wurden - d.h. nicht dass es welche gab, sondern nur das der Unterdrückungsmechanismus aktiv war.

Mit Hilfe der ucId können Sie dann einen Eintrag herausholen.



## Einen Eintrag finden und Daten auslesen

Mit diesem Aufruf bekommen Sie die Daten eines Eintrages:

```url
https://ihre_ccm19_instanz/api/domain/consents?apikey=IHR_API_KEY&domainId=DOM_ID&ucid=UC_ID
```

Dieser Aufruf zeigt dann die gesamte Consent Historie dieses Key - im Beispiel

```json

[
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
    },
    {
        "consent": true,
        "ucid": "387f1d311b2e7ba1f67722ac08bfdaf56aad3ecab6f11309d0c829f4e255af12",
        "timestamp": 1608208338,
        "purposes": {
            "41ba25c": "Technisch notwendig"
        },
        "embeddings": {
            "16bd7f0": "Papoo CMS Verwaltung der Session"
        },
        "manipulationPrevention": true
    }
]
```

Sie sehen die ucid ist jeweils identisch und die Consents haben unterschiedliche Zeitstempel.