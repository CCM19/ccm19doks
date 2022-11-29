# Domain

## Übersicht

| Beschreibung                               | Methode  | Endpunkt                                           |
| ------------------------------------------ | -------- | -------------------------------------------------- |
| [Domain erstellen](#create-domain)         | `POST`   | `/hosting/api/client/{clientId}/domain`            |
| [Alle Domains auslesen](#read-all-domains) | `GET`    | `/hosting/api/client/{clientId}/domain`            |
| [Domain auslesen](#read-domain)            | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}` |
| [Domain aktualisieren](#update-domain)     | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}` |
| [Domain entfernen](#delete-domain)         | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}` |

## Domain erstellen {#create-domain}

**Endpunkt:** `/hosting/api/client/{clientId}/domain`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos

**Payload:** [Domain](../components.md#domain)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Domain](../components.md#domain)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Domains auslesen {#read-all-domains}

**Endpunkt:** `/hosting/api/client/{clientId}/domain`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos

**Response:**

- `200` – Erfolg
  - [Domain](../components.md#domain)\[]

## Domain auslesen {#read-domain}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [Domain](../components.md#domain)
- `404` – Ressource nicht gefunden

## Domain aktualisieren {#update-domain}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Domain](../components.md#domain)

**Response:**

- `200` – Erfolg
  - [Domain](../components.md#domain)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Domain entfernen {#delete-domain}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden
