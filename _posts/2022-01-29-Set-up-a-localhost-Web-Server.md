---
title: Set up a localhost Web Server for Faster Website Development
---

Two approaches: DNS approach and hosts file approach. The DNS approach is more convenient as it doesn't require modifications to the hosts file and virtual host config file each time a new virtual host is added. The small catch is that the DNS approach relies on third party service such as `http://localhost.tv/`.

## DNS Approach

### 1. Enable virtual host alias and virtual host config

In Apache `conf` folder, open `httpd.conf`, uncomment `LoadModule vhost_alias_module modules/mod_vhost_alias.so`. Also uncomment `Include conf/extra/httpd-vhosts.conf`.

### 2. Config virtual host

In Apache `conf\extra` folder, open `httpd-vhosts.conf`, add the following lines:

```
<VirtualHost *:80>
  ServerName catchall.localhost.tv
  ServerAlias *.localhost.tv
  VirtualDocumentRoot "C:\Users\[user]\Documents\%1"
  <Directory "C:\Users\[user]\Documents">
    Require all granted
  </Directory>
</VirtualHost>
```

Only need to do this once. `%1` means the first part of dot-separated components of the server name, i.e. `*`.

### 3. Access the virtual host

Create any folder, e.g. `[site]` under the virtual root `C:\Users\[user]\Documents`. Place an `index.html` file in the folder. It can then be access via `[site].localhost.tv`.

## hosts File Approach

### 1. Config hosts file

Open Notepad as administrator, open `C:\Windows\System32\drivers\etc\hosts`.

In the hosts file, add the following line: `127.0.0.1 site1.localhost`

Repeat for other virtual servers.

### 2. Enable virtual host config

In Apache `conf` folder, open `httpd.conf`, uncomment `Include conf/extra/httpd-vhosts.conf`.

### 3. Config virtual host

In Apache `conf\extra` folder, open `httpd-vhosts.conf`, add the following lines:

```
<VirtualHost *:80>
  ServerName site1.localhost
  DocumentRoot "C:\Users\[user]\Documents\site1"
  <Directory "C:\Users\[user]\Documents\site1">
    Require all granted
  </Directory>
</VirtualHost>
```

### 4. Access the virtual host

Create a folder `site1` under the virtual root `C:\Users\[user]\Documents`. Place an `index.html` file in the folder. It can then be access via `site1.localhost`.

To add another virtual host say `site2.localhost`, repeat step 1 and step 2 and add entries for `site2` accordingly.
