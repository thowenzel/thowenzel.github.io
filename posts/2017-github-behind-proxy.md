extends: default.liquid

title: Github für Windows hinter Proxy
date:       16 Jan 2017 00:00:00 +0000
humandate:  16.01.2017
tags: github, proxy
path: archiv
---

Nach der Installation von **Github für Windows** im Büro stellte ich fest, das ich leider hinter einem Proxy sitze. Um **Github für Windows** für die Nutzung mit Proxy zu konfigurieren gibt es derzeit noch keine Einstellung in der GUI.
Daher muss die Datei `.gitconfig` unter `C:\Benutzer\<Ihr Benutzername>\gitconfig` oder `C:\Dokumente und Einstellungen\<Ihr Benutzername>\gitconfig` angepasst werden.

Also fix die Datei öffnen und folgende Zeilen (anpassen) einfügen:

```
[http]
proxy = http://yourproxy:8080

[https]
proxy = https://yourproxy.com:8080
```