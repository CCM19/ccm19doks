# Locale

## Übersicht

| Beschreibung                                     | Methode  | Endpunkt                                                     |
| ------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [Übersetzung erstellen](#create-locale)          | `POST`   | `/hosting/api/client/{clientId}/domain/{domainId}/locale`    |
| [Alle Übersetzungen auslesen](#read-all-locales) | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/locale`    |
| [Übersetzung auslesen](#read-locale)             | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}` |
| [Übersetzung aktualisieren](#update-locale)      | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}` |
| [Übersetzung entfernen](#delete-locale)          | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}` |

## Übersetzung erstellen {#create-locale}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/locale`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Locale](../components.md#locale)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Locale](../components.md#locale)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Übersetzungen auslesen {#read-all-locales}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/locale`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [Locale](../components.md#locale)[]

## Übersetzung auslesen {#read-locale}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{localeName}`: *string* – Die Name der zu behandelnden Ressource

**Response:**

- `200` – Erfolg
  - [Locale](../components.md#locale)
- `404` – Ressource nicht gefunden

## Übersetzung aktualisieren {#update-locale}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{localeName}`: *string* – Die Name der zu behandelnden Ressource

**Payload:** [Locale](../components.md#locale)

**Response:**

- `200` – Erfolg
  - [Locale](../components.md#locale)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Übersetzung entfernen {#delete-locale}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/locale/{localeName}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{localeName}`: *string* – Die Name der zu behandelnden Ressource

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden

