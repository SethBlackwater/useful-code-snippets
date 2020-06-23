# Useful code snippets
Some of the most useful codes snippets around.



## .htaccess

### Force HTTPS on all requests
```
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```
Source: https://www.siteground.com/kb/how-to-force-ssl-with-htaccess/


### Add trailing slash
```
RewriteCond %{REQUEST_URI} !(/$|\.) 
RewriteRule (.*) %{REQUEST_URI}/ [R=301,L] 
```
Source: https://stackoverflow.com/a/11880879/7872728

