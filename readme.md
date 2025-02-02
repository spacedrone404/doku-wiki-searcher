﻿Search the library registry by specified criteria.
 
Search for letters, numbers, phrases, whatever.

Tested in > 8000 lines of text environment.

Powered by DokuWiki:
https://www.dokuwiki.org/dokuwiki 

Minimal system requirements: i3 / 2Gb RAM

Recommended system requirements: i5 / 4Gb RAM + SSD

Operating system: Windows 7 / Linux

Browser: Firefox 78 ESR and up

Technology stack: Apache, Html, Css, Markdown, Php, Js, Ajax, Batch, Power shell. 

<img src="https://cloud.disroot.org/s/aqGtJEsGsykqZGK/download/doku-wiki-searcher.png" width="512px"/>

Windows users:

1] !run.cmd is only for Windows

2] To work out-of-the-box software should be placed into C:\dokuwiki\

Linux users:

1] Just start Apache with following configuration

```
Listen 8800
ServerName microapache
ServerRoot .
DocumentRoot ./../dokuwiki
ServerAdmin webmaster@example.com

# load apache modules
LoadModule access_compat_module modules/mod_access_compat.so
LoadModule authz_core_module modules/mod_authz_core.so
LoadModule dir_module modules/mod_dir.so
LoadModule mime_module modules/mod_mime.so
LoadModule rewrite_module modules/mod_rewrite.so

# Load PHP module and add handler
LoadModule php7_module php/php7apache2_4.dll
AddHandler application/x-httpd-php .php

# Configure the path to php.ini
PHPIniDir php

# Increase Stacksize to 8MB but use fewer threads -> 192MB RAM usage
# see Issue #3
<IfModule mpm_winnt_module>
    ThreadStackSize 8388608
    ThreadsPerChild 64
</IfModule>

AcceptPathInfo off
KeepAlive on
KeepAliveTimeout 15
TimeOut 30
DirectoryIndex index.html index.php

# allow .htaccess overrides
<Directory ./../dokuwiki>
    AllowOverride All
</Directory>
<Directory .>
    AllowOverride None
</Directory>
```


2] And head on to http://localhost:8800 

