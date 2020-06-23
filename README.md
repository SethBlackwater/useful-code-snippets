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


### Force WWW before domain name
```
RewriteEngine On
RewriteCond %{HTTP_HOST} !=""
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteCond %{HTTPS}s ^on(s)|
RewriteRule ^ http%1://www.%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
```
>NOTE: This will redirect ALL subdomains to www

Source: https://stackoverflow.com/a/4958847/7872728


### Wordpress default htaccess
```
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
```
Source: https://wordpress.org/support/article/htaccess/


### Block certain IP addresses
```
Order Allow,Deny
Deny from 66.249.74.10
Allow from all
```
Source: https://stackoverflow.com/a/18483210/7872728

### Block range of IP addresses
```
Order Allow,Deny
Deny from 66.249.74.0/24
Allow from all
```
Source: https://stackoverflow.com/a/18483210/7872728
