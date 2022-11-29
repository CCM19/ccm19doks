# Komponenten

Die folgenden Komponenten beschreiben die Datenstruktur, wie sie bei Anfragen an die Hosting-API erwartet und wie sie als Antwort von der Hosting-API erwartet werden kann.

**Bei fettgedruckten Eigenschaften handelt es sich um Pflichtfelder, zudem sind diese mit einem Asterisk gekennzeichnet.**

## Übersicht

| Name                                                         | Beschreibung                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Client](#client)                                            | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [Domain](#domain)                                            | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [Locale](#locale)                                            | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [Theme](#theme)                                              | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [Placeholder](#placeholder)                                  | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [Embedding](#embedding)                                      | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [EmbeddingAsset](#embedding-asset)                           | Der Deskriptor für die Struktur der Ressource, wie er von der API erwartet und gesendet wird. |
| [OnboardingScanResult](#onboarding-scan-result)              | Der Deskriptor für die Daten, die von der API nach dem Scannen einer Domain gesendet werden. |
| [OnboardingPreset](#onboarding-preset)                       | Der Deskriptor für die Daten, wie er beim Importieren einer Vorlage erwartet wird. |
| [OnboardingPresetResult](#onboarding-preset-result)          | Der Deskriptor für die Daten, die von der API gesendet werden, nachdem eine Vorlage importiert wurde. |
| [OnboardingCookie](#onboarding-cookie)                       |                                                              |
| [OnboardingEmbedCodeSnippets](#onboarding-embed-code-snippets) | Der Deskriptor für die Daten, die von der API bei der Anforderung von Code-Schnipseln zur Einbindung von CCM19 gesendet werden. |

## Client {#client}

| Eigenschaft                    | Datentyp | Lesen | Schreiben | Beschreibung                                                 |
| ------------------------------ | -------- | ----- | --------- | ------------------------------------------------------------ |
| `id`                           | *string* | ✅     | ❌         |                                                              |
| **`username`** (*)             | *string* | ✅     | ✅         |                                                              |
| **`password`** (*)             | *string* | ❌     | ✅         | Das Passwort des Kunden in Klartext; alternativ `passwordHash` verwenden.<br /><br />**Nur zur Erzeugung eines Kunden erforderlich. Feld weglassen, um das Passwort unverändert zu lassen.** |
| `passwordHash`                 | *string* | ✅     | ✅         | Ein vorberechneter Passwort-Hash (bcrypt: *$2y$*); `password` hat Vorrang |
| `active`                       | *bool*   | ✅     | ✅         | Gibt an, ob sich der Kunde einloggen kann.<br />*(Standardwert: false)* |
| `firstName`                    | *string* | ✅     | ✅         |                                                              |
| `lastName`                     | *string* | ✅     | ✅         |                                                              |
| **`emailAddress`** (*)         | *string* | ✅     | ✅         |                                                              |
| `company`                      | *string* | ✅     | ✅         |                                                              |
| `domainCount`                  | *int*    | ✅     | ❌         |                                                              |
| `domainMaxCount`               | *int*    | ✅     | ✅         | Maximale Anzahl an Domains, die ein Kunde in seinem Account verwalten kann; -1 ist unbegrenzt.<br />*(Standardwert: 0)* |
| `whitelabelCount`              | *int*    | ✅     | ❌         |                                                              |
| `whitelabelMaxCount`           | *int*    | ✅     | ✅         | Maximale Anzahl an Whitelabel-Lizenzen, die einem Kunden zur Verfügung stehen; -1 ist unbegrenzt.<br />*(Standardwert: 0)* |
| `widgetDisplayCount`           | *int*    | ✅     | ❌         |                                                              |
| `widgetDisplayMaxCount`        | *int*    | ✅     | ✅         | Legt fest, wie häufig das CCM19-Widget im Frontend pro Monat geladen wird; -1 ist unbegrenzt.<br />*(Standardwert: 0)* |
| `autoCreateDomains`            | *bool*   | ✅     | ✅         | *(Standardwert: false)*                                      |
| [`features`](#client.features) | *object* | ✅     | ✅         | Funktionen, die der Kunde nutzen darf.                       |

 (*) Diese Eigenschaften sind Pflichtfelder.

### Client.features {#client.features}

| Eigenschaft             | Datentyp | Lesen | Schreiben | Beschreibung                                                 |
| ----------------------- | -------- | ----- | --------- | ------------------------------------------------------------ |
| `canUseABTests` | *bool* | ✅     | ✅         |                                                              |
| `canUseAnalytics` | *bool* | ✅     | ✅         |                                                              |
| `canUseConsentSharing` | *bool* | ✅     | ✅         |                                                              |
| `canUseDomAPI` | *bool* | ✅     | ✅         |                                                              |
| `canUseIAB` | *bool* | ✅     | ✅         |                                                              |
| `canUseIframeCSS` | *bool* | ✅     | ✅         |                                                              |
| `canUseIframes` | *bool* | ✅     | ✅         |                                                              |
| `canUseIndCSS` | *bool* | ✅     | ✅         |                                                              |
| `canUseMultiDom` | *bool* | ✅     | ✅         |                                                              |
| `canUseOwnLogo` | *bool* | ✅     | ✅         |                                                              |
| `canUseScripts` | *bool* | ✅     | ✅         |                                                              |
| `canUseUserGroupRights` | *bool* | ✅     | ✅         |                                                              |
| `moreThan2Lang` | *bool* | ✅     | ✅         |                                                              |

## Domain {#domain}

| Eigenschaft                                      | Datentyp   | Lesen | Schreiben | Beschreibung                                                 |
| ------------------------------------------------ | ---------- | ----- | --------- | ------------------------------------------------------------ |
| `id`                                             | *string*   | ✅     | ❌         |                                                              |
| **`name`** (*)                                   | *string*   | ✅     | ✅         | Wird wie das Eingabefeld [Domainname](../../verwaltung/domainverwaltung.md#eintrag-bearbeiten) der Domainverwaltung behandelt, kann beim Schreiben also zusätzlich den Pfad einer Website definieren.<br />Beispiele:<br />`www.mysite.xyz`<br />`www.mysite.xyz/website2/`<br />`https://www.mysite.xyz`<br />`https://www.mysite.xyz/website2/`<br />Beim Auslesen der Eigenschaft wird **nur der Domainname**, für die oberen Beispiele also `www.mysite.xyz`, zurückgegeben. Der Pfad steht dabei in der read-only Eigenschaft `path`. |
| `path`                                           | *string*   | ✅     | ❌         | Liest den Pfad aus, der mit `name` gesetzt werden kann; standardmäßig `/`. |
| `country`                                        | *?string*  | ✅     | ✅         | ISO 3166-1 alpha-2 Ländercode (AT,DE,CH,GB,US usw.); "ZZ" zur Angabe eines unbekannten Landes; oder `null`, um auf die Profilkonfiguration des Benutzers zurückzugreifen. |
| `whitelabel`                                     | *bool*     | ✅     | ✅         |                                                              |
| `consentStorage`                                 | *string*   | ✅     | ✅         | Zulässige Werte:<br />`cookie` `localStorage` `sessionStorage`<br />*(Standardwert: `localStorage`)* |
| `consentCookieLifetime`                          | *int*      | ✅     | ✅         |                                                              |
| `consentCookieSecure`                            | *bool*     | ✅     | ✅         |                                                              |
| `consentResetBeforeDate`                         | *date*     | ✅     | ✅         | Format: "YYYY-MM-DD"                                         |
| `consentResetOnLegalChange`                      | *bool*     | ✅     | ✅         |                                                              |
| `consentSharingDomains`                          | *string[]* | ✅     | ✅         |                                                              |
| `consentSharingCrossDomain`                      | *bool*     | ✅     | ✅         |                                                              |
| `frontendWidgetEnabled`                          | *bool*     | ✅     | ✅         |                                                              |
| `frontendWidgetCache`                            | *bool*     | ✅     | ✅         |                                                              |
| `frontendWidgetMinifyCode`                       | *bool*     | ✅     | ✅         |                                                              |
| `managementStructure`                            | *string*   | ✅     | ✅         | Zulässige Werte:<br />`cookie` `embedding`<br />*(Standardwert: `embedding`)*<br /><br />**Die Verwaltungsstruktur `cookie` ist veraltet, es werden keine API-Endpunkte mehr bereitgestellt.** |
| `deleteUnknownCookies`                           | *bool*     | ✅     | ✅         |                                                              |
| `deleteUnknownCookiesForceReload`                | *bool*     | ✅     | ✅         |                                                              |
| `requireConsentForMandatoryEmbeddings`           | *bool*     | ✅     | ✅         |                                                              |
| `declineButtonEnforced`                          | *bool*     | ✅     | ✅         |                                                              |
| `allowedScriptMarkers`                           | *string[]* | ✅     | ✅         |                                                              |
| `blockedScriptMarkers`                           | *string[]* | ✅     | ✅         |                                                              |
| `evalInlineScripts`                              | *bool*     | ✅     | ✅         | *(Standardwert: false)*                                      |
| `recordScriptsOnWebsite`                         | *bool*     | ✅     | ✅         |                                                              |
| `blockNewScripts`                                | *bool*     | ✅     | ✅         |                                                              |
| `blockFirstPartyScripts`                         | *bool*     | ✅     | ✅         |                                                              |
| `blockInlineScripts`                             | *bool*     | ✅     | ✅         |                                                              |
| `permanentScanEnabled`                           | *bool*     | ✅     | ✅         |                                                              |
| `tcfEnabled`                                     | *bool*     | ✅     | ✅         |                                                              |
| `tcfEnableNewVendorsAfterGvlUpdate`              | *bool*     | ✅     | ✅         |                                                              |
| `tcfVendorBlacklist`                             | *int[]*    | ✅     | ✅         |                                                              |
| `tcfSpecialFeatures`                             | *int[]*    | ✅     | ✅         |                                                              |
| `tcfGoogleAdditionalConsentMode`                 | *bool*     | ✅     | ✅         |                                                              |
| `tcfGoogleAdditionalConsentAdProviders`          | *int[]*    | ✅     | ✅         |                                                              |
| `tcfUrlMacroAutoAppend`                          | *bool*     | ✅     | ✅         |                                                              |
| `tcfUrlMacroHandling`                            | *bool*     | ✅     | ✅         |                                                              |
| `blockIframes`                                   | *bool*     | ✅     | ✅         |                                                              |
| `rememberIframeConsentPerDomain`                 | *bool*     | ✅     | ✅         |                                                              |
| `appendConsentSwitchToIframes`                   | *bool*     | ✅     | ✅         |                                                              |
| `iframeBlockMode`                                | *string*   | ✅     | ✅         | Zulässige Werte:<br />`blacklist` `whitelist`<br />*(Standardwert: `whitelist`)* |
| `iframeMarkers`                                  | *string[]* | ✅     | ✅         |                                                              |
| `cookieDeclarationTableHeadingStartLevel`        | *int*      | ✅     | ✅         | Zulässige Werte:<br />`2` `3` `4` `5`<br />*(Standardwert: `3`)* |
| `cookieDeclarationTablePrependConsentChangeLink` | *bool*     | ✅     | ✅         |                                                              |
| `cookieDeclarationTablePrependIntroText`         | *bool*     | ✅     | ✅         |                                                              |
| `imprintDisplayMode`                             | *string*   | ✅     | ✅         | Zulässige Werte:<br />`direct` `link`<br />*(Standardwert: `link`)* |
| `imprintOpenInNewTab`                            | *bool*     | ✅     | ✅         |                                                              |
| `imprintShowWidget`                              | *bool*     | ✅     | ✅         |                                                              |
| `privacyPolicyDisplayMode`                       | *string*   | ✅     | ✅         | Zulässige Werte:<br />`direct` `link`<br />*(Standardwert: `link`)* |
| `privacyPolicyOpenInNewTab`                      | *bool*     | ✅     | ✅         |                                                              |
| `privacyPolicyShowWidget`                        | *bool*     | ✅     | ✅         |                                                              |
| `accessibilityDisplayMode`                       | *string*   | ✅     | ✅         | Zulässige Werte:<br />`direct` `link`                        |
| `accessibilityLinkEnabled`                       | *bool*     | ✅     | ✅         | *(Standardwert: false)*                                      |

 (*) Diese Eigenschaften sind Pflichtfelder.

## Locale {#locale}

| Eigenschaft                                      | Datentyp                                | Lesen | Schreiben | Beschreibung                                                 |
| ------------------------------------------------ | --------------------------------------- | ----- | --------- | ------------------------------------------------------------ |
| **`name`** (*)                                   | *string*                                | ✅     | ❌         | Nur erlaubt, um eine Ressource zu erzeugen.                  |
| `active`                                         | *bool*                                  | ✅     | ✅         |                                                              |
| `widgetTitle`                                    | *string*                                | ✅     | ✅         |                                                              |
| `widgetIntroText`                                | *string*                                | ✅     | ✅         |                                                              |
| `widgetDeclineButtonText`                        | *string*                                | ✅     | ✅         |                                                              |
| `widgetFullConsentButtonText`                    | *string*                                | ✅     | ✅         |                                                              |
| `widgetSettingsButtonText`                       | *string*                                | ✅     | ✅         |                                                              |
| `checkAllButtonText`                             | *string*                                | ✅     | ✅         |                                                              |
| `uncheckAllButtonText`                           | *string*                                | ✅     | ✅         |                                                              |
| `imprint`                                        | *string*                                | ✅     | ✅         |                                                              |
| `imprintHtmlCode`                                | *string*                                | ✅     | ✅         |                                                              |
| `imprintUrl`                                     | *string*                                | ✅     | ✅         |                                                              |
| `privacyPolicy`                                  | *string*                                | ✅     | ✅         |                                                              |
| `privacyPolicyHtmlCode`                          | *string*                                | ✅     | ✅         |                                                              |
| `privacyPolicyUrl`                               | *string*                                | ✅     | ✅         |                                                              |
| `accessibility`                                  | *string*                                | ✅     | ✅         |                                                              |
| `accessibilityHtmlCode`                          | *string*                                | ✅     | ✅         |                                                              |
| `accessibilityUrl`                               | *string*                                | ✅     | ✅         |                                                              |
| `categoriesTitle`                                | *string*                                | ✅     | ✅         |                                                              |
| `categoriesCancelButtonText`                     | *string*                                | ✅     | ✅         |                                                              |
| `categoriesFullConsentButtonText`                | *string*                                | ✅     | ✅         |                                                              |
| `categoriesSaveButtonText`                       | *string*                                | ✅     | ✅         |                                                              |
| `detailsTitle`                                   | *string*                                | ✅     | ✅         |                                                              |
| `detailsCloseButtonText`                         | *string*                                | ✅     | ✅         |                                                              |
| `embeddingVendorLabel`                           | *string*                                | ✅     | ✅         |                                                              |
| `embeddingDescriptionLabel`                      | *string*                                | ✅     | ✅         |                                                              |
| `embeddingPrivacyPolicyUrlLabel`                 | *string*                                | ✅     | ✅         |                                                              |
| `embeddingLifetimeLabel`                         | *string*                                | ✅     | ✅         |                                                              |
| `embeddingWhichDataIsCollectedLabel`             | *string*                                | ✅     | ✅         |                                                              |
| `embeddingPurposeOfDataCollectionLabel`          | *string*                                | ✅     | ✅         |                                                              |
| `embeddingLegalBasisLabel`                       | *string*                                | ✅     | ✅         |                                                              |
| `embeddingPlaceOfProcessingLabel`                | *string*                                | ✅     | ✅         |                                                              |
| `embeddingAssetNameLabel`                        | *string*                                | ✅     | ✅         |                                                              |
| `embeddingAssetLifetimeLabel`                    | *string*                                | ✅     | ✅         |                                                              |
| `embeddingAssetDescriptionLabel`                 | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentTitle`                            | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentDisclaimer`                       | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentConsentButtonText`                | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentConsentSwitchShowExternalContent` | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentConsentSwitchAllowEmbedding`      | *string*                                | ✅     | ✅         |                                                              |
| `blockedContentConsentSwitchProviderDetails`     | *string*                                | ✅     | ✅         |                                                              |
| `purposeNames`                                   | *Object.&lt;purposeId, name&gt;*        | ✅     | ✅         | `41ba25c`: Technisch notwendig<br />`cdcbd7c`: Anzeigen / Ads<br />`a717ff5`: Analyse / Statistiken<br />`7c19e32`: Personalisierung<br />`6cd2721`: Social Media<br />`15c61c3`: Sonstiges |
| `purposeDescriptions`                            | *Object.&lt;purposeId, description&gt;* | ✅     | ✅         | `41ba25c`: Technisch notwendig<br />`cdcbd7c`: Anzeigen / Ads<br />`a717ff5`: Analyse / Statistiken<br />`7c19e32`: Personalisierung<br />`6cd2721`: Social Media<br />`15c61c3`: Sonstiges |
| `changeConsentText`                              | *string*                                | ✅     | ✅         |                                                              |
| `moreInformationLabel`                           | *string*                                | ✅     | ✅         |                                                              |
| `questionMarkButtonText`                         | *string*                                | ✅     | ✅         |                                                              |
| `tcfVendorIntroText`                             | *string*                                | ✅     | ✅         |                                                              |
| `tcfPurposeLabel`                                | *string*                                | ✅     | ✅         |                                                              |
| `tcfSpecialPurposeLabel`                         | *string*                                | ✅     | ✅         |                                                              |
| `tcfFeaturesLabel`                               | *string*                                | ✅     | ✅         |                                                              |
| `tcfSpecialFeaturesLabel`                        | *string*                                | ✅     | ✅         |                                                              |
| `tcfOptedInRemark`                               | *string*                                | ✅     | ✅         |                                                              |
| `tcfThirdPartiesLabel`                           | *string*                                | ✅     | ✅         |                                                              |
| `nonTcfPurposesLabel`                            | *string*                                | ✅     | ✅         |                                                              |
| `nonTcfVendorsLabel`                             | *string*                                | ✅     | ✅         |                                                              |
| `tcfVendorUsesNonCookieStorageText`              | *string*                                | ✅     | ✅         |                                                              |
| `tcfSpecialFeaturesHandledGloballyText`          | *string*                                | ✅     | ✅         |                                                              |
| `tcfStacksListText`                              | *string*                                | ✅     | ✅         |                                                              |
| `tcfCookieRefreshText`                           | *string*                                | ✅     | ✅         |                                                              |
| `tcfExtendedDisclosureText`                      | *string*                                | ✅     | ✅         |                                                              |
| `tcfAssetTypeLabel`                              | *string*                                | ✅     | ✅         |                                                              |
| `tcfAssetPurposesLabel`                          | *string*                                | ✅     | ✅         |                                                              |

 (*) Diese Eigenschaften sind Pflichtfelder.

## Theme {#theme}

| Eigenschaft                                  | Datentyp   | Lesen | Schreiben | Beschreibung                                                 |
| -------------------------------------------- | ---------- | ----- | --------- | ------------------------------------------------------------ |
| `id`                                         | *string*   | ✅     | ❌         |                                                              |
| **`name`** (*)                               | *string*   | ✅     | ✅         |                                                              |
| `default`                                    | *bool*     | ✅     | ✅         |                                                              |
| `widgetBlocking`                             | *bool*     | ✅     | ✅         |                                                              |
| `widgetButtons`                              | *string[]* | ✅     | ✅         | Zulässige Werte:<br />`accept` `decline` `cpanel`            |
| `widgetCloseButton`                          | *bool*     | ✅     | ✅         |                                                              |
| `widgetPosition`                             | *string*   | ✅     | ✅         | Zulässige Werte:<br />`top` `center` `bottom` `bottomleft` `bottomright` |
| `widgetSwitchType`                           | *string*   | ✅     | ✅         |                                                              |
| `showPurposesInMainWindow`                   | *bool*     | ✅     | ✅         |                                                              |
| `settingsAcceptAllButton`                    | *bool*     | ✅     | ✅         |                                                              |
| `settingsCheckAndUncheckAllButtons`          | *bool*     | ✅     | ✅         |                                                              |
| `settingsFooter`                             | *bool*     | ✅     | ✅         |                                                              |
| `complyWithDoNotTrack`                       | *bool*     | ✅     | ✅         |                                                              |
| `enableOnlyInEu`                             | *bool*     | ✅     | ✅         |                                                              |
| `manipulationPrevention`                     | *bool*     | ✅     | ✅         |                                                              |
| `logoEnabled`                                | *bool*     | ✅     | ✅         |                                                              |
| `logoImage`                                  | *?string*  | ✅     | ✅         | Kodierung: Base64<br />Maximale Größe: 512 KiB<br />Erlaubte MIME-Types: `image/jpeg` `image/png`<br /><br />Übergebe `null`, um das hinterlegte Bild zu entfernen. |
| `settingsIconEnabled`                        | *bool*     | ✅     | ✅         |                                                              |
| `settingsIconImage`                          | *?string*  | ✅     | ✅         | Kodierung: Base64<br />Maximale Größe: 64 KiB<br />Erlaubte MIME-Types: `image/jpeg` `image/png`<br /><br />Übergebe `null`, um das hinterlegte Bild zu entfernen. |
| `settingsIconTarget`                         | *string*   | ✅     | ✅         | Zulässige Werte:<br />`main` `purpose`<br />*(Standardwert: `purpose`)* |
| `whitelabel`                                 | *bool*     | ✅     | ✅         |                                                              |
| **`primaryButtonBackgroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`primaryButtonForegroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`primaryButtonBorderColor`** (*)           | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`declineButtonBackgroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`declineButtonForegroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`declineButtonBorderColor`** (*)           | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`buttonBackgroundColor`** (*)              | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`buttonForegroundColor`** (*)              | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`buttonBorderColor`** (*)                  | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`windowBackgroundColor`** (*)              | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`windowForegroundColor`** (*)              | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`windowLinkColor`** (*)                    | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`windowBorderColor`** (*)                  | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`iframeBlockerBackgroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`iframeBlockerForegroundColor`** (*)       | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`iframeBlockerButtonBackgroundColor`** (*) | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| **`iframeBlockerButtonForegroundColor`** (*) | *string*   | ✅     | ✅         | Format: "#rrggbb"                                            |
| `customCss`                                  | *string*   | ✅     | ✅         |                                                              |
| `customCssForIframeBlocker`                  | *string*   | ✅     | ✅         |                                                              |

 (*) Diese Eigenschaften sind Pflichtfelder.

## Placeholder  {#placeholder}

| Eigenschaft     | Datentyp | Lesen | Schreiben | Beschreibung                                |
| --------------- | -------- | ----- | --------- | ------------------------------------------- |
| **`name`** (*)  | *string* | ✅     | ❌         | Nur erlaubt, um eine Ressource zu erzeugen. |
| **`value`** (*) | *string* | ✅     | ✅         |                                             |

 (*) Diese Eigenschaften sind Pflichtfelder.

## Embedding {#embedding}

| Eigenschaft               | Datentyp                                                     | Lesen | Schreiben | Beschreibung                                                 |
| ------------------------- | ------------------------------------------------------------ | ----- | --------- | ------------------------------------------------------------ |
| `id`                      | *string*                                                     | ✅     | ❌         |                                                              |
| **`name`** (*)            | *string*                                                     | ✅     | ✅         |                                                              |
| `active`                  | *bool*                                                       | ✅     | ✅         |                                                              |
| **`purpose`** (*)         | *string*                                                     | ✅     | ✅         | `41ba25c`: Technisch notwendig<br />`cdcbd7c`: Anzeigen / Ads<br />`a717ff5`: Analyse / Statistiken<br />`7c19e32`: Personalisierung<br />`6cd2721`: Social Media<br />`15c61c3`: Sonstiges |
| `vendor`                  | *string*                                                     | ✅     | ✅         |                                                              |
| `scriptHtmlCode`          | *string*                                                     | ✅     | ✅         |                                                              |
| `scriptLoaderGroup`       | *string*                                                     | ✅     | ✅         |                                                              |
| `scriptMarkers`           | *string[]*                                                   | ✅     | ✅         |                                                              |
| `iframeMarkers`           | *string[]*                                                   | ✅     | ✅         |                                                              |
| `hideIframesUntilConsent` | *bool*                                                       | ✅     | ✅         |                                                              |
| `excludeUrlsMode`         | *string*                                                     | ✅     | ✅         |                                                              |
| `excludeFromUrls`         | *string[]*                                                   | ✅     | ✅         |                                                              |
| `description`             | *string*                                                     | ✅     | ✅         |                                                              |
| `privacyPolicyUrl`        | *string*                                                     | ✅     | ✅         |                                                              |
| `whatDataIsCollected`     | *string*                                                     | ✅     | ✅         |                                                              |
| `purposeOfDataCollection` | *string*                                                     | ✅     | ✅         |                                                              |
| `legalBasis`              | *string*                                                     | ✅     | ✅         |                                                              |
| `placeOfProcessing`       | *string*                                                     | ✅     | ✅         |                                                              |
| `translations`            | Object.&lt;localeName, [translation](#embedding.translations.item)&gt; | ✅     | ✅         | Verwenden Sie Gebietsschema-Namen, um jede Übersetzung als eine separate Eigenschaft zu definieren.<br />`de_DE` `en_US` `fr_FR` `es_ES` `pt_PT` `it_IT` `nl_NL` `pl_PL` `ru_RU` `zh` `ja` `cs` … |
| `tcfVendor`               | *?int*                                                       | ✅     | ✅         | Entweder eine gültige TCF-Anbieter-ID oder `null`, um den Verweis zu entfernen. Diese Eigenschaft hat Vorrang vor der Eigenschaft `vendor` und überschreibt sie mit dem jeweiligen Anbieternamen. |
| `tcfPurposes`             | *int[]*                                                      | ✅     | ✅         |                                                              |
| `tcfSpecialFeatures`      | *int[]*                                                      | ✅     | ✅         |                                                              |
| `googleConsentMode`       | *string[]*                                                   | ✅     | ✅         | Zulässige Werte:<br />`ad_storage` `analytics_storage` `functionality_storage` `personalization_storage` `security_storage` |
| `assets`                  | [EmbeddingAsset](#embedding-asset)[]                         | ✅     | ✅         | **Stapelaktion, bei der vorhandene Assets entfernt werden**; also Vorsicht. Empfohlen für POST-Anfragen. |

(*) Diese Eigenschaften sind Pflichtfelder.

### Embedding.translations.[] {#embedding.translations.item}

| Eigenschaft                | Datentyp | Lesen | Schreiben | Beschreibung                                        |
| -------------------------- | -------- | ----- | --------- | --------------------------------------------------- |
| `name`                     | *string* | ✅     | ✅         | Optionale Übersetzung für den Namen der Einbindung. |
| `description`              | *string* | ✅     | ✅         |                                                     |
| `privacyPolicyUrl`         | *string* | ✅     | ✅         |                                                     |
| `whatDataIsCollected`      | *string* | ✅     | ✅         |                                                     |
| `purposeOfDataCollection`  | *string* | ✅     | ✅         |                                                     |
| `legalBasis`               | *string* | ✅     | ✅         |                                                     |
| `placeOfProcessing`        | *string* | ✅     | ✅         |                                                     |
| `blockedContentTitle`      | *string* | ✅     | ✅         |                                                     |
| `blockedContentText`       | *string* | ✅     | ✅         |                                                     |
| `blockedContentButtonText` | *string* | ✅     | ✅         |                                                     |

## EmbeddingAsset {#embedding-asset}

| Eigenschaft    | Datentyp                                                     | Lesen | Schreiben | Beschreibung                                                 |
| -------------- | ------------------------------------------------------------ | ----- | --------- | ------------------------------------------------------------ |
| `id`           | *string*                                                     | ✅     | ❌         |                                                              |
| **`name`** (*) | *string*                                                     | ✅     | ✅         |                                                              |
| `dynamic`      | *bool*                                                       | ✅     | ✅         |                                                              |
| `storageType`  | *string*                                                     | ✅     | ✅         | Zulässige Werte:<br />`cookie` `localStorage` `sessionStorage` `indexedDb` `webSql` `other` |
| `lifetime`     | *string*                                                     | ✅     | ✅         |                                                              |
| `description`  | *string*                                                     | ✅     | ✅         |                                                              |
| `translations` | Object.&lt;localeName, [translation](#embedding-asset.translations.item)&gt; | ✅     | ✅         | Verwenden Sie Gebietsschema-Namen, um jede Übersetzung als eine separate Eigenschaft zu definieren.<br />`de_DE` `en_US` `fr_FR` `es_ES` `pt_PT` `it_IT` `nl_NL` `pl_PL` `ru_RU` `zh` `ja` `cs` … |

(*) Diese Eigenschaften sind Pflichtfelder.

### EmbeddingAsset.translations.[] {#embedding-asset.translations.item}

| Eigenschaft   | Datentyp | Lesen | Schreiben | Beschreibung                                                 |
| ------------- | -------- | ----- | --------- | ------------------------------------------------------------ |
| `lifetime`    | *string* | ✅     | ✅         | Ungefähre Lebensdauer des Eintrags – z. B. "1 Stunde" oder "5 Tage". |
| `description` | *string* | ✅     | ✅         | Wofür wird der Eintrag (Cookie, Local-Storage usw.) verwendet? |

## OnboardingScanResult {#onboarding-scan-result}

| Eigenschaft                                                  | Datentyp   | Lesen | Schreiben | Beschreibung                                                 |
| ------------------------------------------------------------ | ---------- | ----- | --------- | ------------------------------------------------------------ |
| [`address`](#onboarding-scan-result.address)                 | *object*   | ✅     | ❌         | Diese Daten können z. B. zur Aktualisierung von [Platzhaltern](./endpoints/placeholder.md) verwendet werden. |
| `imprintUrl`                                                 | *?string*  | ✅     | ❌         |                                                              |
| `privacyPolicyUrl`                                           | *?string*  | ✅     | ❌         |                                                              |
| [`availablePresets`](#onboarding-scan-result.available-presets.item) | *object[]* | ✅     | ❌         |                                                              |
| [`storage`](#onboarding-scan-result.storage)                 | *object*   | ✅     | ❌         |                                                              |

### OnboardingScanResult.address {#onboarding-scan-result.address}

| Eigenschaft | Datentyp  | Lesen | Schreiben | Beschreibung                                                 |
| ----------- | --------- | ----- | --------- | ------------------------------------------------------------ |
| `company`   | *?string* | ✅     | ❌         | Hierbei kann es sich z. B. um die Firma oder auch den Namen des Seitenbetreibers handeln, je nach Informationen, die auf der Impressum-Seite gefunden werden. |
| `street`    | *?string* | ✅     | ❌         |                                                              |
| `zipCode`   | *?string* | ✅     | ❌         |                                                              |
| `city`      | *?string* | ✅     | ❌         |                                                              |

### OnboardingScanResult.availablePresets.[] {#onboarding-scan-result.available-presets.item}

| Eigenschaft    | Datentyp                                                     | Lesen | Schreiben | Beschreibung                                                 |
| -------------- | ------------------------------------------------------------ | ----- | --------- | ------------------------------------------------------------ |
| `id`           | *int*                                                        | ✅     | ❌         | Als [OnboardingPreset.id](#onboarding-preset) verwenden.     |
| `name`         | *string*                                                     | ✅     | ❌         |                                                              |
| `purpose`      | *string*                                                     | ✅     | ❌         | `41ba25c`: Technisch notwendig<br />`cdcbd7c`: Anzeigen / Ads<br />`a717ff5`: Analyse / Statistiken<br />`7c19e32`: Personalisierung<br />`6cd2721`: Social Media<br />`15c61c3`: Sonstiges |
| `vendor`       | *string*                                                     | ✅     | ❌         |                                                              |
| `translations` | Object.&lt;localeName, [translation](#onboarding-scan-result.available-presets.translations.item)&gt; | ✅     | ❌         | Sprachen werden durch den Eigenschaftsnamen einer Übersetzung identifiziert. |

#### OnboardingScanResult.availablePresets.translations.[] {#onboarding-scan-result.available-presets.translations.item}

| Eigenschaft   | Datentyp | Lesen | Schreiben | Beschreibung |
| ------------- | -------- | ----- | --------- | ------------ |
| `name`        | *string* | ✅     | ❌         |              |
| `description` | *string* | ✅     | ❌         |              |

### OnboardingScanResult.storage {#onboarding-scan-result.storage}

| Eigenschaft                                                  | Datentyp   | Lesen | Schreiben | Beschreibung |
| ------------------------------------------------------------ | ---------- | ----- | --------- | ------------ |
| [`cookies`](#onboarding-scan-result.storage.cookies.item)    | *object[]* | ✅     | ❌         |              |
| [`localStorage`](#onboarding-scan-result.storage.local-storage.item) | *object[]* | ✅     | ❌         |              |
| [`sessionStorage`](#onboarding-scan-result.storage.session-storage.item) | *object[]* | ✅     | ❌         |              |

#### OnboardingScanResult.storage.cookies.[] {#onboarding-scan-result.storage.cookies.item}

| Eigenschaft | Datentyp | Lesen | Schreiben | Beschreibung |
| ----------- | -------- | ----- | --------- | ------------ |
| `name`      | *string* | ✅     | ❌         |              |
| `domain`    | *string* | ✅     | ❌         |              |
| `path`      | *string* | ✅     | ❌         |              |

#### OnboardingScanResult.storage.localStorage.[] {#onboarding-scan-result.storage.local-storage.item}

| Eigenschaft | Datentyp | Lesen | Schreiben | Beschreibung |
| ----------- | -------- | ----- | --------- | ------------ |
| `name`      | *string* | ✅     | ❌         |              |

#### OnboardingScanResult.storage.sessionStorage.[] {#onboarding-scan-result.storage.session-storage.item}

| Eigenschaft | Datentyp | Lesen | Schreiben | Beschreibung |
| ----------- | -------- | ----- | --------- | ------------ |
| `name`      | *string* | ✅     | ❌         |              |

## OnboardingPreset {#onboarding-preset}

| Eigenschaft  | Datentyp | Lesen | Schreiben | Beschreibung                                                 |
| ------------ | -------- | ----- | --------- | ------------------------------------------------------------ |
| **`id`** (*) | *int*    | ❌     | ✅         |                                                              |
| `active`     | *bool*   | ❌     | ✅         | Ressource beim Erzeugen sofort aktivieren.<br />*(Standardwert: false)* |

(*) Diese Eigenschaften sind Pflichtfelder.

## OnboardingPresetResult {#onboarding-preset-result}

| Eigenschaft   | Datentyp | Lesen | Schreiben | Beschreibung                           |
| ------------- | -------- | ----- | --------- | -------------------------------------- |
| `presetId`    | *int*    | ✅     | ❌         |                                        |
| `embeddingId` | *string* | ✅     | ❌         | Die ID der soeben erzeugten Ressource. |

## OnboardingCookie {#onboarding-cookie}

| Eigenschaft   | Datentyp | Lesen | Schreiben | Beschreibung                           |
| ------------- | -------- | ----- | --------- | -------------------------------------- |
| **`name`** (*) | *string*    | ❌    | ✅        |                                        |
| **`storageType`** (*) | *string* | ❌    | ✅        | Zulässige Werte:<br />`cookie` `localStorage` `sessionStorage` |

(*) Diese Eigenschaften sind Pflichtfelder.

## OnboardingEmbedCodeSnippets {#onboarding-embed-code-snippets}

| Eigenschaft       | Datentyp | Lesen | Schreiben | Beschreibung                                                 |
| ----------------- | -------- | ----- | --------- | ------------------------------------------------------------ |
| `default`         | *string* | ✅     | ❌         | Dieser Code-Schnipsel zeigt direkt auf die CCM19-Konfiguration einer jeweiligen Domain. Es wird das Theme verwendet, das als aktiv markiert ist; die Sprache wird bei jeder Anfrage automatisch ermittelt. |
| `de_DE, en_US, …` | *string* | ✅     | ❌         | Für jede aktive Übersetzung existiert eine separate Eigenschaft, die den Code-Schnipsel zum Erzwingen der jeweiligen Sprache enthält. |

