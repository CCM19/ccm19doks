# Verwendete Technik

Wir setzen auf weltweit millionenfach bewährte Standards bei der Umsetzung von CCM19. Die Grundlage der Software ist das PHP-Framework [Symfony©](https://symfony.com/), mit über 600.000 Entwicklern weltweit eines der bewährtesten und sichersten Frameworks, die zur Verfügung stehen.

## Frontend-Widgets

Die Frontend-Widgets werden durch pures Javascript realisiert, ohne Rückgriff auf Frameworks um mögliche Inkompatibilitäten möglichst zu vermeiden.

## Sicherheit

CCM19 nutzt intensiv [Content Security Policy (CSP)](https://content-security-policy.com/) mit regulär folgenden Einschränkungen:

```
Content-Security-Policy:
	default-src 'self';
	connect-src 'self' https://update.ccm19.de;
	script-src 'self' 'unsafe-inline';
	style-src 'self' 'unsafe-inline';
	img-src 'self' data:;
	frame-ancestors 'self';
	form-action 'self'
```

## Speicherung

Alle Daten werden im JSON-Format lokal im gesicherten Bereich von CCM19 gespeichert. Wenn Sie die Downloadvariante nutzen finden Sie die Daten im Verzeichnis */var* Ihrer Installation.

Die Speicherung und Verarbeitung ist so effizient, dass auch mehrere Millionen Aufrufe pro Tag problemlos gehändelt werden können.

## Datenbank

CCM19 nutzt derzeit kein Datenbank-Management-System.

## Beta-Phase

Vor der Veröffentlichung führen wir diverse Tests durch um typische Fehler zu finden und zu korrigieren. Weiterhin gibt es eine ausgedehnte Beta Phase an der viele Kunden teilnehmen und uns Feedback vor der endgültigen Veröffentlichung geben.

## Systemvoraussetzungen für Download-Variante

Die Self-Service / Download Version von CCM19 benötigt lediglich

- Linux oder ein anderes POSIX-kompatibles Betriebssystem
- PHP ab Version 7.2
- Apache httpd 2.2+ oder nginx

### Apache httpd

Als Server empfehlen wir einen LAMP-Server – wobei das M für MySQL nicht notwendig ist, da derzeit keine Datenbank genutzt wird.

Beim Betrieb mit Apache httpd werden folgende Module benötigt:

- mod_rewrite
- mod_headers (optional)
- mod_expires (optional)

CCM19 ist mit dem Caching-Modul mod_cache vollständig kompatibel.

### nginx

Sollte ihr Webserver **nginx** verwenden, sind unter Umständen Anpassungen an der Serverkonfiguration nötig, damit CCM19 zufriedenstellend läuft, nachdem Sie den ersten Schritt der Installation durchgeführt haben.

Bringen Sie zunächst den Pfad zur Konfigurationsdatei des nginx-Servers für Ihre (Sub-)Domain (üblicherweise /etc/nginx/nginx.conf oder /etc/nginx/conf.d/*domainname*.conf) und den Socket-Pfad für das installierte PHP-FPM-Modul (häufig unix:/run/php/php7.2-fpm.sock o.ä.) bei Ihrem Provider oder Server-Administrator in Erfahrung.

Notieren Sie bitte weiterhin den absoluten Pfad zum public-Verzeichnis der CCM19-Installation und den gewünschten URL-Pfad zu ccm19 (z.B. /ccm19).

Die hier aufgeführte Beispiel-Konfigurationsdatei finden Sie im Downloadpaket im Verzeichnis *www/examples/* - hier wird ccm19 in einem Unterverzeichnis installiert.

Beispiel:

```
# Fügen Sie den Inhalt dieser Datei Ihrer nginx-Konfiguration innerhalb eines
# server-Blocks hinzu, wenn Sie CCM19 in einem Unterverzeichnis betreiben wollen.
# Dazu wird das PHP-FPM-Modul mit mindestens PHP 7.2 benötigt.
#
# Sie müssen folgende Anpassungen vornehmen:
# - "/ccm19" durch den URL-Pfad ersetzen unter dem CCM19 erreichbar sein soll,
# - "/path/to/ccm/public" durch den Pfad zum public-Verzeichnis in Ihrer
#   CCM19-Installation (ohne / am Ende!) ersetzen,
# - "unix:/run/php/php7.2-fpm.sock" je nach Serverkonfiguration durch den
#   Socket-Pfad zu Ihrem PHP-FPM-Modul ersetzen.

	set $ccm19_urlpath /ccm19;
	set $ccm19_realpath /path/to/ccm/public;

	location ~ /ccm19(/.*) {
		root $ccm19_realpath;
		try_files $1 @ccm19;
	}

	location ^~ /ccm19/index.php {
		return 403;
	}

	location @ccm19 {
		root $ccm19_realpath;

		fastcgi_index index.php;
		fastcgi_split_path_info ^(/ccm19)(/.*)$;
		set $path_info $fastcgi_path_info;

		fastcgi_param SCRIPT_FILENAME $document_root/index.php;
		fastcgi_param SCRIPT_NAME $ccm19_urlpath/index.php;
		fastcgi_param PATH_INFO $path_info;

		fastcgi_param HTTP_PROXY	"";
		fastcgi_param QUERY_STRING	$query_string;
		fastcgi_param REQUEST_METHOD	$request_method;
		fastcgi_param CONTENT_TYPE	$content_type;
		fastcgi_param CONTENT_LENGTH	$content_length;
		fastcgi_param REQUEST_URI	$request_uri;
		fastcgi_param DOCUMENT_URI	$document_uri;
		fastcgi_param DOCUMENT_ROOT	$document_root;
		fastcgi_param SERVER_PROTOCOL	$server_protocol;
		fastcgi_param REQUEST_SCHEME	$scheme;
		fastcgi_param HTTPS		$https if_not_empty;
		fastcgi_param GATEWAY_INTERFACE	CGI/1.1;
		fastcgi_param SERVER_SOFTWARE	nginx/$nginx_version;
		fastcgi_param REMOTE_ADDR	$remote_addr;
		fastcgi_param REMOTE_PORT	$remote_port;
		fastcgi_param SERVER_ADDR	$server_addr;
		fastcgi_param SERVER_PORT	$server_port;
		fastcgi_param SERVER_NAME	$server_name;

		fastcgi_pass unix:/run/php/php7.2-fpm.sock;
	}

```
