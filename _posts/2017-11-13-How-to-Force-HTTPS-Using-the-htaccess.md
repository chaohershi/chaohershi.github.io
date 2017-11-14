---
title: How to Force HTTPS Using the .htaccess
---

Long story short, I purchased a domain and hosted it with [FastComet](https://www.fastcomet.com/). After setting up the SSL/TLS, I tried to force all web traffic to use HTTPS. One way of doing this would be adding the following rules in the .htaccess file in the website’s root folder.

``` apache
RewriteEngine on
RewriteCond %{HTTPS} off
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

Rules do the same job but written in slightly different syntax:

``` apache
RewriteEngine On 
RewriteCond %{SERVER_PORT} 80 
RewriteRule ^(.*)$ https://%{SERVER_NAME}/$1 [L,R=301]
```

---

Relative Reading:

Tutorial:
- [An In-Depth Guide to mod_rewrite for Apache](https://code.tutsplus.com/tutorials/an-in-depth-guide-to-mod_rewrite-for-apache--net-6708)

Apache Documentations:
- [Apache Module mod_rewrite](https://httpd.apache.org/docs/current/mod/mod_rewrite.html)
- [Apache mod_rewrite Introduction](https://httpd.apache.org/docs/current/rewrite/intro.html)
- [RewriteRule Flags](https://httpd.apache.org/docs/current/rewrite/flags.html)

Others:
- [Moving your website to HTTPS / SSL: tips & tricks • Yoast](https://yoast.com/moving-your-website-to-https-ssl-tips-tricks/)
- [htaccess | CSS-Tricks](https://css-tricks.com/snippets/htaccess/)