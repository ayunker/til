# Fix SSH Connection Hanging on Fedora

I connect to a Fedora box for some development work over SSH. This works great,
but fairly frequently the connection will hang for a couple of seconds. The
keypresses aren't lost, but the display is frozen during this period - making
interactive work difficult. 

Turns out the issue has to do with the wifi power save mode - if power save is
on the wifi radio will sleep between beacons, resulting in the hanging
behavior. I'm not sure how specific this is to my setup, but turning off power
save mode addressed the issue on my Fedora install with an intel wifi card.
YMMV.

For a test, you can run the following. This will persist until a reboot.

``` bash
sudo iw dev <interface> set power_save off

# verify this ouptut of this command is: Power save: off
iw dev <interface> get power_save 
```

If that resolves it, you can make it a permanent change by adding the following
to NetworkManager config (at least on systemd systems). Reboot or restart the
network manager (`sudo systemctl restart NetworkManager`) for the change to
take effect

```
# /etc/NetworkManager/conf.d/wifi-powersave.conf
[connection]
  wifi.powersave = 2
```

via https://til.hashrocket.com/posts/k4yoaohhnc-fix-ssh-connection-hanging-on-fedora
