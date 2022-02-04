# Technique used

We rely on standards proven millions of times worldwide to implement CCM19. The foundation of the software is the PHP framework [Symfony©](https://symfony.com/), one of the most proven and secure frameworks available with over 600,000 developers worldwide.

## Frontend widgets

The frontend widgets are realized by pure javascript, without recourse to frameworks like jquery, vue, react or others to avoid possible incompatibilities as far as possible.

## Security

CCM19 makes intensive use of [Content Security Policy (CSP)](https://content-security-policy.com/) with regular following restrictions:

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

## storage without database

All data is stored in JSON format locally in the secured area of CCM19. If you use the download variant you will find the data in the */var* directory of your installation.

The storage and processing is so efficient that even several million calls per day can be handled without problems.

## Storage with database

CCM19 uses alternatively MongoDB from version 4, in this vairante all data is stored in the database.

## Beta phase

Before the release we do several tests to find and correct typical bugs. Furthermore there is an extended beta phase where many customers participate and give us feedback before the final release.

## System requirements for download version

The self-service / download version of CCM19 only requires

- Linux or another POSIX compatible operating system
- PHP version 7.2 or higher
- Apache httpd 2.2+ or nginx
- And in case of using the database MongoDB version 4 or higher

### Apache httpd

As a server we recommend a LAMP server - where the M for MySQL is not necessary, and is alternatively replaced by MongoDB.

When running with Apache httpd, the following modules are required:

- mod_rewrite
- mod_headers (optional)
- mod_expires (optional)

CCM19 is fully compatible with the caching module mod_cache. Additionally it is recommended to use performance optimization. How to do this, we refer to the countless tutorials that are available on other sites.

### nginx

If your web server uses **nginx**, you may need to make some adjustments to your server configuration to make CCM19 run satisfactorily after you have completed the first step of the installation.

First find out the path to the configuration file of the nginx server for your (sub)domain (usually /etc/nginx/nginx.conf or /etc/nginx/conf.d/*domainname*.conf) and the socket path for the installed PHP FPM module (often unix:/run/php/php7.2-fpm.sock or similar) from your provider or server administrator.

Furthermore, please note the absolute path to the public directory of the CCM19 installation and the desired URL path to ccm19 (e.g. /ccm19).

The sample configuration file listed here can be found in the download package in the directory *www/examples/* - here ccm19 is installed in a subdirectory.

Example:

```
# Add the contents of this file to your nginx configuration inside a
# server block if you want to run CCM19 in a subdirectory.
# This requires the PHP FPM module with at least PHP 7.2.
#
# You will need to make the following adjustments:
# - replace "/ccm19" with the URL path where CCM19 should be accessible,
# - replace "/path/to/ccm/public" with the path to the public directory in your
# CCM19 installation (without / at the end!),
# - replace "unix:/run/php/php7.2-fpm.sock" depending on your server # configuration with the socket path to your PHP
# socket path to your PHP FPM module.

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

		fastcgi_param HTTP_PROXY "";
		fastcgi_param QUERY_STRING $query_string;
		fastcgi_param REQUEST_METHOD $request_method;
		fastcgi_param CONTENT_TYPE $content_type;
		fastcgi_param CONTENT_LENGTH $content_length;
		fastcgi_param REQUEST_URI $request_uri;
		fastcgi_param DOCUMENT_URI $document_uri;
		fastcgi_param DOCUMENT_ROOT $document_root;
		fastcgi_param SERVER_PROTOCOL $server_protocol;
		fastcgi_param REQUEST_SCHEME $scheme;
		fastcgi_param HTTPS $https if_not_empty;
		fastcgi_param GATEWAY_INTERFACE CGI/1.1;
		fastcgi_param SERVER_SOFTWARE nginx/$nginx_version;
		fastcgi_param REMOTE_ADDR $remote_addr;
		fastcgi_param REMOTE_PORT $remote_port;
		fastcgi_param SERVER_ADDR $server_addr;
		fastcgi_param SERVER_PORT $server_port;
		fastcgi_param SERVER_NAME $server_name;

		fastcgi_pass unix:/run/php/php7.2-fpm.sock;
	}

```
