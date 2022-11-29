# Das Einstellungsicon unten links stört mich, kann ich das ändern/entfernen?

Das sogenannte Einstellungsicon ist in unseren Designvorlagen standardmäßig aktiviert, kann aber leicht abgeschaltet werden. Gehen Sie dazu in die Theme-Verwaltung und deaktivieren die entsprechende Funktion beim genutzten Theme:

![assets.png](../../assets/assets.png)

Weiter unten auf der Seite können Sie das Icon auch gegen ein eigenes austauschen:

![einstellungsicon-aendern.png](../../assets/einstellungsicon-aendern.png)

Rein rechtlich sind Sie dazu verpflichtet dem Nutzer zu jeder Zeit die Möglichkeit zu geben, auf die Einstellungen zugreifen zu können und seine Zustimmung revideren zu lassen. Den Link zum Öffnen des Banners finden Sie auch unter dem Menüpunkt [Dashboard & Einbindung](/funktionen/dashboard/#konfigurationsbox-erneut-offnen-per-link). Es ist ein einfacher Link mit Anker:

```
<a href="#" onclick="CCM.openWidget();return false;">Konfigurationsbox öffnen</a>
```
