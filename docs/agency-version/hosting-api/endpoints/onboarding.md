# Onboarding

## Übersicht

| Beschreibung                                                                 | Methode | Endpunkt                                                                            |
| ---------------------------------------------------------------------------- | ------- | ----------------------------------------------------------------------------------- |
| [Domain scannen](#scan-domain)                                               | `GET`   | `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/scan`                  |
| [Vorlagen importieren](#import-presets)                                      | `POST`  | `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/presets`               |
| [Einbindungen aus Cookies erzeugen](#embeddings-from-cookies)                | `POST`  | `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/embeddingsFromCookies` |
| [Code-Schnipsel zur Einbindung von CCM19 auslesen](#get-embed-code-snippets) | `GET`   | `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/embed`                 |

## Domain scannen {#scan-domain}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/scan`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [OnboardingScanResult](../components.md#onboarding-scan-result)
- `400` – Die Website hat einen fehlerhaften Antwortcode oder einen leeren Inhalt gesendet
- `404` – Ressource nicht gefunden
- `500` – Beim Crawlen der Website ist ein Problem aufgetreten

## Vorlagen importieren {#import-presets}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/presets`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [OnboardingPreset](../components.md#onboarding-preset)\[]

**Response:**

- `201` – Ressource erfolgreich erzeugt
  - [OnboardingPresetResult](../components.md#onboarding-preset-result)\[]
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Einbindungen aus Cookies erzeugen {#embeddings-from-cookies}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/embeddingsFromCookies`

**Methode:** `POST`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Payload:** [OnboardingCookie](../components.md#onboarding-cookie)\[]

**Response:**

- `201` – Ressource(n) erfolgreich erzeugt
- `400` – Ungültige oder fehlende Eigenschaften
- `404` – Ressource nicht gefunden

## Code-Schnipsel zur Einbindung von CCM19 auslesen {#get-embed-code-snippets}

**Endpunkt:** `/hosting/api/client/{clientId}/domain/{domainId}/onboarding/embed`

**Methode:** `GET`

**Query:**

- `{clientId}`: *string* – Die ID eines CCM19-Kundenkontos
- `{domainId}`: *string* – Die ID einer Domain, die in dem Kundenkonto vorhanden ist

**Response:**

- `200` – Erfolg
  - [OnboardingEmbedCodeSnippets](../components.md#onboarding-embed-code-snippets)
- `404` – Ressource nicht gefunden
