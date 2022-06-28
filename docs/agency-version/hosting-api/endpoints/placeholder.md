# Placeholder

## Übersicht

| Beschreibung                                                 | Methode  | Endpunkt                                                     |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [Platzhalter erstellen](#create-placeholder)                 | `POST`   | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder` |
| [Alle Platzhalter überschreiben (bulk)](#create-placeholder-bulk) | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder` |
| [Alle Platzhalter auslesen](#read-all-placeholders)          | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder` |
| [Platzhalter auslesen](#read-placeholder)                    | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}` |
| [Platzhalter aktualisieren](#update-placeholder)             | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}` |
| [Platzhalter entfernen](#delete-placeholder)                 | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}` |

## Platzhalter erstellen {#create-placeholder}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Placeholder](../components.md#placeholder)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Placeholder](../components.md#placeholder)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Platzhalter überschreiben (bulk) {#create-placeholder-bulk}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Placeholder](../components.md#placeholder)[]

**Response:**

- `201` – Ressource(n) erfolgreich erzeugt
  - [Placeholder](../components.md#placeholder)[]
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Platzhalter auslesen {#read-all-placeholders}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [Placeholder](../components.md#placeholder)[]

## Platzhalter auslesen {#read-placeholder}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{placeholderName}`: *string* – Die Name der zu behandelnden Ressource

**Response:**

- `200` – Erfolg
  - [Placeholder](../components.md#placeholder)
- `404` – Ressource nicht gefunden

## Platzhalter aktualisieren {#update-placeholder}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{placeholderName}`: *string* – Die Name der zu behandelnden Ressource

**Payload:** [Placeholder](../components.md#placeholder)

**Response:**

- `200` – Erfolg
  - [Placeholder](../components.md#placeholder)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Platzhalter entfernen {#delete-placeholder}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/placeholder/{placeholderName}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{placeholderName}`: *string* – Die Name der zu behandelnden Ressource

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden

