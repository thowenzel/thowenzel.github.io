title: Linux-Server absichern
published_date: "2018-01-23 00:00:00 +0000"
layout: default.liquid
is_draft: true
data:
  tags: "linux, server, security"
  humandate: 23.01.2018
---
__Standard-SSH-Port des Servers ändern__

Eine einfache Änderung, die aber zumindest automatisierte Brute-Force-Attacken auf den üblicherweise genutzten Port 22 ins leeren laufen lässt.
Dazu die SSH-Konfigurations-Datei öffnen:
```
nano /etc/ssh/sshd_config
```

In der Datei den Port von 22 auf einen Wert zwischen 49152 und 65535 setzen. Anschließend SSH neu starten:
```
systemctl restart sshd.service
```

#### Weiterführende Links:
* [Linux-basierte Root-Server absichern (mit Checkliste)](https://www.thomas-krenn.com/de/tkmag/allgemein/linux-basierte-root-server-absichern/)
* [4 Tipps, wie Sie Ihren (Virtual)Server gegen Hacking-Attacken schützen](https://www.hosteurope.de/blog/4-tipps-wie-sie-ihren-virtualserver-gegen-hacking-attacken-schuetzen/)
* [Root Server absichern](https://www.rechenkraft.net/wiki/Root_Server_absichern_(Ubuntu_14.04))
