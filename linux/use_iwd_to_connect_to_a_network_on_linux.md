# Use iwd to Connect to a Network on Linux

If you're in a fresh install of linux and stuck on the command line but need to
connect to wifi, you can use the iNet Wireless Daemon (`iwd`) by interacting
with it via it's client `iwctl`. Once you start up the `iwctl` command prompt,
you can scan and connect to a wireless network.

```shell
$ iwctl
[iwd]# device list # find the name of your device, likely wlan0 for wifi
[iwd]# station wlan0 scan # scan for networks
[iwd]# station wlan0 get-networks # list available networks from the scan
[iwd]# station wlan0 connect [SSID] # connect to your network
```

[Docs](https://wiki.archlinux.org/title/Iwd)
