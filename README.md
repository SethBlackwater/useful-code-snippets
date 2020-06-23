# Useful code snippets
Some of the most useful codes snippets around.



## .htaccess
Force HTTPS on all requests.
```
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

