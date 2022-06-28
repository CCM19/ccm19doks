# Client

## Übersicht

| Beschreibung                              | Methode  | Endpunkt                                |
| ----------------------------------------- | -------- | --------------------------------------- |
| [Kunden erstellen](#create-client)        | `POST`   | `/hosting/api/client`                   |
| [Alle Kunden auslesen](#read-all-clients) | `GET`    | `/hosting/api/client`                   |
| [Kunden auslesen](#read-client)           | `GET`    | `/hosting/api/client/{clientId}`        |
| [Kunden aktualisieren](#update-client)    | `PUT`    | `/hosting/api/client/{clientId}`        |
| [Kunden entfernen](#delete-client)        | `DELETE` | `/hosting/api/client/{clientId}`        |
| [Kundensuche](#client-search)             | `GET`    | `/hosting/api/clientgetid/{searchTerm}` |

## Kunden erstellen {#create-client}

**Endpunkt:** `/hosting/api/client`

**Methode:** `POST`

**Payload:** [Client](../components.md#client)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Client](../components.md#client)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Kunden auslesen {#read-all-clients}

**Endpunkt:** `/hosting/api/client`

**Methode:** `GET`

**Response:**

- `200` – Erfolg
  - [Client](../components.md#client)[] – Spezifisch für diesen Endpunkt enthält jedes Element zusätzlich folgende Eigenschaften:
    - `actualCallCount`: *int*
    - `domainCountData`: *Array.&lt;domainName, callCount&gt;*

## Kunden auslesen {#read-client}

**Endpunkt:** `/hosting/api/client/{clientId}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos

**Response:**

- `200` – Erfolg
  - [Client](../components.md#client)
- `404` – Ressource nicht gefunden

## Kunden aktualisieren {#update-client}

**Endpunkt:** `/hosting/api/client/{clientId}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos

**Payload:** [Client](../components.md#client)

**Response:**

- `200` – Erfolg
  - [Client](../components.md#client)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Kunden entfernen {#delete-client}

**Endpunkt:** `/hosting/api/client/{clientId}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden

## Kundensuche {#client-search}

**Endpunkt:** `/hosting/api/clientgetid/{searchTerm}`

**Methode:** `GET`

**Query:**

- `{searchTerm}`: *string* – Benutzername oder E-Mail-Adresse

**Response:**

- `200` – Erfolg
  - [Client](../components.md#client)
- `404` – Ressource nicht gefunden