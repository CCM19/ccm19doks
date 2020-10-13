# Google Tag Manager

Über den DataLayer wird im Google Tag Manager für jedes Cookie, das erlaubt wird, ein „Custom Event" ausgelöst:

```
CCM19.cookieAccepted.<cookiename>
```

Also z.B. `CCM19.cookieAccepted._ga` für das Cookie **_ga**.

Im Tag Manager kann über Triggers → New → Custom Events darauf reagiert werden.

Work in Progress...