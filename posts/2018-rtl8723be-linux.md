title: WLAN-Modul RTL8723BE with Linux
published_date: "2018-02-12 00:00:00 +0000"
layout: default.liquid
data:
  tags: "linux, archlinux"
  humandate: 12.02.2018
---
Because my good old Toshiba notebook died some days ago, a new one had to come. My choice fell on a cheap 15" device from [HP](https://www.notebooksbilliger.de/hp+15+ay107ng+notebook/). I admit, I did not research for a long time. So there was a likelihood that I would encounter problems installing Linux. The distribution of my choice has been Arch Linux for some time. Contrary to my fears, the installation went smoothly.

However, the reception performance of the WLAN module left much to be desired. Although a WLAN connection was possible in principle, but only if the WLAN was in the immediate vicinity. 2 meters away from the router I still had moderate reception, a few meters further he was completely gone.

So I first of all determined, which hardware module is exactly installed:
```
lspci -nnk | grep -i network -A2
```

After it was so clear that in my laptop is the module RTL8723BE, I was able to search the web specifically for information. I was probably not the first one with the problem, so I quickly found out more information. On the website below I found a solution that works for me too.

#### Related links:
* [Anleitung: Realtek WLAN und Bluetooth unter Linux (RTL8723BE)](https://www.au-ja.de/guide-realtek-wlan+bluetooth-unter-linux-%28rtl8723be%29-1.phtml)
