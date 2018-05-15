title: Pacman Tipps&Tricks
permalink: "/2018/pacman_hints.html"
published_date: "2018-05-03 00:00:00 +0000"
layout: default.liquid
is_draft: false
data:
  tags: "linux, arch linux, arch"
  humandate: 03.05.2018
---
__Arch-Mirrorliste aktualisieren und optimieren__

Die Mirrorliste wird über das Paket *pacman-mirrorlist* regelmäßig aktualisiert. Allerdings kann es hilfreich sein, diese Liste etwas auszumisten und die Server nach optimaler Erreichbarkeit zu sortieren.
Das lässt sich über die Shell einfach durchführen:
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

Fetchmirrors holt sich die aktuelle Mirrorliste aus dem Netz. Anschließend muss die gewünschte Länderliste ausgewählt werden — Für Deutschland also die 12. Anschließend optimiert das Skript die Liste mittels *rankmirrors* und spielt die reduzierte Version ins System ein (dazu fordert es kurz Root-Rechte an).
Sollte einer der Mirror irgendwann mal merklich klemmen, einfach *fetchmirrors* neu ausführen, oder Liste nochmal per Hand optimieren.

#### Weiterführende Links:
* [Mirrors sortieren](https://wiki.archlinux.org/index.php/Mirrors#Sorting_mirrors)