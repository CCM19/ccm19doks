# Embedding

## Übersicht

| Beschreibung                                       | Methode  | Endpunkt                                                     |
| -------------------------------------------------- | -------- | ------------------------------------------------------------ |
| [Einbindung erstellen](#create-embedding)          | `POST`   | `/hosting/api/client/{clientId}/domain/{domainId}/embedding` |
| [Alle Einbindungen auslesen](#read-all-embeddings) | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding` |
| [Einbindung auslesen](#read-embedding)             | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}` |
| [Einbindung aktualisieren](#update-embedding)      | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}` |
| [Einbindung entfernen](#delete-embedding)          | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}` |

## Einbindung erstellen {#create-embedding}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Embedding](../components.md#embedding)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Embedding](../components.md#embedding)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Einbindungen auslesen {#read-all-embeddings}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [Embedding](../components.md#embedding)[]

## Einbindung auslesen {#read-embedding}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `200` – Erfolg
  - [Embedding](../components.md#embedding)
- `404` – Ressource nicht gefunden

## Einbindung aktualisieren {#update-embedding}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID der zu behandelnden Ressource

**Payload:** [Embedding](../components.md#embedding)

**Response:**

- `200` – Erfolg
  - [Embedding](../components.md#embedding)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Einbindung entfernen {#delete-embedding}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden

