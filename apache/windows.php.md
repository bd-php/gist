## Apache PHP Windows Portable Install
* [Download Apache for windows](https://www.apachelounge.com/)
* Extract it to ` D:\apache `
* Edit ` httpd.conf ` by adding following lines
```sh
LoadModule php7_module D:/Tools/php/php7apache2_4.dll

<IfModule php7_module>
    DirectoryIndex index.html index.php
    AddHandler application/x-httpd-php .php
    PHPIniDir "D:/Tools/php"
</IfModule>
```

* Add Server Name by adding
```sh
ServerName localhost
```
* Start By
```sh
httpd.exe
```
