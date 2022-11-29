# Theme

## Übersicht

| Beschreibung                             | Methode  | Endpunkt                                                           |
| ---------------------------------------- | -------- | ------------------------------------------------------------------ |
| [Theme erstellen](#create-theme)         | `POST`   | `/hosting/api/client/{clientId}/domain/{domainId}/theme`           |
| [Alle Themes auslesen](#read-all-themes) | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/theme`           |
| [Theme auslesen](#read-theme)            | `GET`    | `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}` |
| [Theme aktualisieren](#update-theme)     | `PUT`    | `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}` |
| [Theme entfernen](#delete-theme)         | `DELETE` | `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}` |

## Theme erstellen {#create-theme}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/theme`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [Theme](../components.md#theme)

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [Theme](../components.md#theme)
- `400` – Ungültige oder fehlende Eigenschaften

## Alle Themes auslesen {#read-all-themes}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/theme`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [Theme](../components.md#theme)\[]

## Theme auslesen {#read-theme}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{themeId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `200` – Erfolg
  - [Theme](../components.md#theme)
- `404` – Ressource nicht gefunden

## Theme aktualisieren {#update-theme}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}`

**Methode:** `PUT`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{themeId}`: *string* – Die ID der zu behandelnden Ressource

**Payload:** [Theme](../components.md#theme)

**Response:**

- `200` – Erfolg
  - [Theme](../components.md#theme)
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Theme entfernen {#delete-theme}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/theme/{themeId}`

**Methode:** `DELETE`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist
- `{themeId}`: *string* – Die ID der zu behandelnden Ressource

**Response:**

- `204` – Ressource erfolgreich gelöscht
- `404` – Ressource nicht gefunden
