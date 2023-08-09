# B760-i9-13900k

OpenCore config for my Raptor Lake desktop containing:

- ASUS prime B760-PLUS
- i9 13900k with Be Quiet pure loop 360 mm AIO
- be quiet! Pure Power 11 500W
- AMD Radeon rx 460
- Samsung 990 pro M.2 NVMe drive (Arch Linux)
- Samsung 850 EVO SATA 500 GB (GhostBSD + Ubuntu)
- Samsung 850 EVO SATA 250 GB (macOS Ventura)
- Kingston SATA 128 GB (win 10)
- 32 GB corsair DDR5-5600 RAM
- ASUS DRW-24D5MT
- be quiet! PURE BASE 600 case

Working:

- the machine boots, and show both displays
- accelerated graphics with native AMD driver
- sound works with alcid 11 (jack, USB audio, HDMI/DP audio).
- on board ethernet (intel) works
- all USB ports work
- appletv+ playback with shikigva=128
- sleep/resume with following pmset options:

```
➜  ~ sudo pmset -g
System-wide power settings:
Currently in use:
 standby              0
 Sleep On Power Button 1
 womp                 1
 hibernatefile        /var/vm/sleepimage
 proximitywake        0
 powernap             0
 networkoversleep     0
 disksleep            0
 standbydelayhigh     86400
 sleep                1 (sleep prevented by UserEventAgent)
 autopoweroffdelay    259200
 hibernatemode        0
 autopoweroff         0
 ttyskeepawake        1
 displaysleep         10
 tcpkeepalive         0
 highstandbythreshold 50
 standbydelaylow      86400
```

What doesn't work:
nothing (well, I don't know about apple services like handover and stuff as I don't use those. I guess it works).
