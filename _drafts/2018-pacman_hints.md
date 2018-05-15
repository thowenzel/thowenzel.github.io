title: Pacman Tipps&Tricks
published_date: "2018-05-03 00:00:00 +0000"
layout: default.liquid
is_draft: true
data:
  tags: "linux, arch linux, arch"
  humandate: 03.05.2018
---
__Arch-Mirrorliste aktualisieren und optimieren__

Die Mirrorliste wird über das Paket pacman-mirrorlist regelmäßig aktualisiert, allerdings ist es hilfreich diese Liste ein wenig auszumisten und nach optimaler Erreichbarkeit zu sortieren. Das lässt sich in der Shell recht einfach durchführen:
```
$ sudo -s
$ cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup
$ sed -i 's/^#Server/Server/' /etc/pacman.d/mirrorlist.backup
$ rankmirrors -n 6 /etc/pacman.d/mirrorlist.backup > /etc/pacman.d/mirrorlist
$ exit
```

Hinweis: Mit dem zweiten Befehl werden alle Kommentare aus der Liste entfernt und somit praktisch jeder Mirrorserver „aktiviert“. Das dritte Kommando geht die Server durch und misst die Erreichbarkeit. Anschließend reduziert *rankmirrors* die Liste auf die besten 6 Mirrorserver und entsorgt den Rest.

Man kann jedoch aber alternativ auch auf das kleine Tool *fetchmirrors* zurückgreifen (im AUR zu finden):
```
$ pacaur -S fetchmirrors
$ fetchmirrors
```

Fetchmirrors holt sich die aktuelle Mirrorliste aus dem Netz und bittet euch anschließend die für euch entsprechend zuständige Länderliste auszuwählen — Für Deutschland also die 12. Anschließend optimiert das Skript die Liste mittels rankmirrors und spielt die reduzierte Version ins System ein — dazu fordert das Programm kurz Root-Rechte an. So klappert die Arch-Paketverwaltung nur noch die für euch am besten erreichbaren Arch-Mirrors ab. Mittels pacman -Syu ruft ihr dann wie gewohnt die Paketquellen ab und spielt die neusten Updates ein. Sollte einer der Mirror irgendwann mal spürbar klemmen, führt ihr einfach nochmal fetchmirrors aus oder optimiert die Liste bei Bedarf nochmal per Hand.

#### Weiterführende Links:
* [Mirrors sortieren](https://wiki.archlinux.org/index.php/Mirrors#Sorting_mirrors)