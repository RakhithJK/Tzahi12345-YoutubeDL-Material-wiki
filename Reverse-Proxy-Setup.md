## Introduction

Using a reverse-proxy channels all YoutubeDL-Material requests through your web server, allowing you to easily enable SSL and take advantage of features like load-balancing. Explore the different approaches with your favorite web server.

NOTE: These apache2 configurations are less tested than the nginx ones. If you encounter any errors, please open an issue [here](https://github.com/Tzahi12345/YoutubeDL-Material/issues).

## Apache2

### On domain root

Not much is required, just add these lines to your virtual host:

	ProxyPass / http://example.com:8998
	ProxyPassReverse / http://example.com:8998

And you'll be good to go!

### Using domain subpath

If you want to run YoutubeDL-Material in a subpath (e.g. `https://example.com/ytdl` instead of `https://example.com`), the configuration requires additional lines compared to instances on the document root. This is an example config where the desired path is `/ytdl`

	ProxyPass /ytdl http://example.com:8998
	ProxyPassReverse /ytdl http://example.com:8998
	ProxyPass /api/ http://example.com:8998
	ProxyPassReverse /api/ http://example.com:8998

	<Location /ytdl>
	  RewriteRule /ytdl/(.*) /$1
	</Location>

	RewriteRule ^/api/(.*) http://example.com:8998/api/$1 [P,QSA]

Note the additional ProxyPass through /api/ and rewrite rules to ensure the app's requests get sent to the right place.

## Nginx

### On domain root

This one's pretty simple, your reverse proxy configuration just needs to look like this:

	location / {
		proxy_pass http://example.com:8998;
	}

And you should be good to go!

### Using domain subpath

If you want to run YoutubeDL-Material in a subpath (e.g. `https://example.com/ytdl` instead of `https://example.com`), the configuration requires additional lines compared to instances on the document root. This is an example config where the desired path is `/ytdl`

	location ~/ytdl(.*)$ {
		rewrite /ytdl/(.*) /  break;
		proxy_pass http://example.com:8998;
	}
		
	location /api/ {
		proxy_pass http://example.com:8998;
	}

Note the additional rewrite rule and the required proxying of API calls in the `/api` route.