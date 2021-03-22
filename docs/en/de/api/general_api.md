# Domain API / General API

Mit der domainspezifischen API können Sie Consent und Ereignisdaten pro Domain und über eine gesicherte SSL Schnittstelle in andere Systeme integrieren.

Der Aufruf erfolgt generell mit Ihrem Api Key als GET-Parameter `apiKey` - ohne diesen ist der Aufruf nicht erfolgreich. Jeder Key ist immer nur für einen Account valide.

Der Aufruf erfolgt generell per simplen GET Aufruf im Browser, curl oder eine beliebige andere Möglichkeit Webdaten aufzurufen.

## API testen

Sie können einen Testaufruf durchführen. Nutzen Sie dafür folgenden API-Endpunkt:

```url
GET /api/test
```

Darauf sollte das System folgendermaßen antworten.

```json
{
    "username": "Ihr_Username",
    "apiKey": "IHR_API_KEY"
}
```

## Alle Domains des Accounts listen

Um alle Domains Ihres Accounts zu listen, nutzen Sie bitte folgenden API-Endpunkt.

```url
GET /api/domains
```

Die Antwort sollte folgendermaßen lauten:

```json
[
    {
        "id": "b61cd4a",
        "name": "https:\/\/www.test-xy.de",
        "whiteLabel": false,
        "viewCount": 0
    },
    {
        "id": "1ed845d",
        "name": "test-12.de",
        "whiteLabel": false,
        "viewCount": 0
    }
]
```

Die domId ist die wichtigste Information - damit können Sie weitere Informationen zur Domain holen.

## Alle Consents aus dem Protokoll holen

Mit dem folgenden API-Endpunkt holen Sie alle Consents aus dem aktuellen Datenblock des Protokolls. Bereits archivierte Protokolleinträge werden dabei nicht berücksichtigt. Bitte ersetzen Sie in der url `{domainId}` mit einer Domain-ID aus der obigen Abfrage.

```url
GET /api/domains/{domainId}/consents
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

Mit diesem API-Endpunkt lassen sich die Protokolleinträge nach Consent-ID filtern. Entweder ist diese vollständig anzugeben oder eine Teilzeichenkette beginnend vom Anfang der Consent-ID. Im folgenden Beispiel lassen sich die Einträge also auch mit dem Wert `387f1` für den Parameter `{consentId}`.

Wichtig dabei ist lediglich, dass es nur eine Consent-ID gibt, die mit `387f1` beginnt. **Bei Kollisionen liefert die Anfrage eine leere Liste.**

```url
GET /api/domains/{domainId}/consents/{consentId}
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

Sie sehen, die ucid ist jeweils identisch und die Consents haben unterschiedliche Zeitstempel.