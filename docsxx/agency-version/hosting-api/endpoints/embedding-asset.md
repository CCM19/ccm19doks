# EmbeddingAsset

## Übersicht

| Beschreibung                                        | Methode  | Endpunkt                                                     |
| --------------------------------------------------- | -------- | ------------------------------------------------------------ |
| [Cookie erstellen](#create-embedding-asset)         | `POST`   | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset` |
| [Alle Cookies auslesen](#read-all-embedding-assets) | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset` |
| [Cookie auslesen](#read-embedding-asset)            | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}` |
| [Cookie aktualisieren](#update-embedding-asset)     | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}` |
| [Cookie entfernen](#delete-embedding-asset)         | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}` |

## Cookie erstellen {#create-embedding-asset}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID einer Einbindung, die in der Domain vorhanden ist

**Payload:** [EmbeddingAsset](../components.md#embedding-asset)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [EmbeddingAsset](../components.md#embedding-asset)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Cookies auslesen {#read-all-embedding-assets}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID einer Einbindung, die in der Domain vorhanden ist

**Response:**

- `200` – Erfolg
  - [EmbeddingAsset](../components.md#embedding-asset)[]

## Cookie auslesen {#read-embedding-asset}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID einer Einbindung, die in der Domain vorhanden ist
- `{assetId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `200` – Erfolg
  - [EmbeddingAsset](../components.md#embedding-asset)
- `404` – Ressource nicht gefunden

## Cookie aktualisieren {#update-embedding-asset}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID einer Einbindung, die in der Domain vorhanden ist
- `{assetId}`: *string* – Die ID der zu behandelnden Ressource

**Payload:** [EmbeddingAsset](../components.md#embedding-asset)

**Response:**

- `200` – Erfolg
  - [EmbeddingAsset](../components.md#embedding-asset)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Cookie entfernen {#delete-embedding-asset}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/embedding/{embeddingId}/asset/{assetId}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{embeddingId}`: *string* – Die ID einer Einbindung, die in der Domain vorhanden ist
- `{assetId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden

