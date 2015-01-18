This is a set of html status pages to display on your webserver (Apache2, Nginx...). This is good for you if you like to polish your web server in a way to provide a nice user experience.


## Motivation

I found the default Apache2 error pages sucks in design. It is okay for most of the time, but if you like to have beautiful web pages, it's not good enough. As very few people seems concerned to make beautiful error pages, I decided to create my own http status page set.

## Demo

I personally use those pages on my personal website. You can watch them in action here: http://static.jeznet.org/pub/http-status-page/

## Installation

I provide here a basic example to use with Apache2. It may depend on you, but I like to put my personalised config into `/etc/apache2/conf.d/error.conf` and I put all html pages into `/usr/local/share/apache2/error/`. Feel free to modify paths:

```
<IfModule mod_alias.c>

        Alias /error/ "/usr/local/share/apache2/error/"

        <Directory "/usr/local/share/apache2/error">
                AllowOverride None
                Order allow,deny
                Allow from all
        </Directory>

        ErrorDocument 400 /error/400.html
        ErrorDocument 401 /error/401.html
        ErrorDocument 403 /error/403.html
        ErrorDocument 404 /error/404.html
        ErrorDocument 405 /error/405.html
        ErrorDocument 408 /error/408.html
        ErrorDocument 410 /error/410.html
        ErrorDocument 411 /error/411.html
        ErrorDocument 412 /error/412.html
        ErrorDocument 413 /error/413.html
        ErrorDocument 414 /error/414.html
        ErrorDocument 415 /error/415.html
        ErrorDocument 500 /error/500.html
        ErrorDocument 501 /error/501.html
        ErrorDocument 502 /error/502.html
        ErrorDocument 503 /error/503.html
        ErrorDocument 506 /error/506.html
        
</IfModule>
```

## Notes

Many of those html pages might be useless, especially the 2xx.html. The one you may use are 404.html, 403.html or 500.html. 

## License

Thoses files are licensed under the GNU GENERAL PUBLIC LICENSE 2. Please modify, update, fork, distribute, whatever!
