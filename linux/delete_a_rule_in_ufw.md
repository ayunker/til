# Delete A Rule In UFW

Say you want to delete a rule in your [uncomplicated firewall (ufw)](https://wiki.ubuntu.com/UncomplicatedFirewall). You run `ufw help` and see that the entry for delete is

```
delete RULE|NUM                 delete RULE
```

But when you check the status with `sudo ufw status`, all you see is this

```
Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
443                        ALLOW       Anywhere
OpenSSH (v6)               ALLOW       Anywhere (v6)
443 (v6)                   ALLOW       Anywhere (v6)
```

Where's the rule number?

What you need is `sudo ufw status numbered`, which has the rule number in the left hand column.

```
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] OpenSSH                    ALLOW IN    Anywhere
[ 2] 443                        ALLOW IN    Anywhere
[ 3] OpenSSH (v6)               ALLOW IN    Anywhere (v6)
[ 4] 443 (v6)                   ALLOW IN    Anywhere (v6)
```

So if you want to delete your OpenSSH rule for IPv6, you know to run `sudo ufw delete 3`.

via https://til.hashrocket.com/posts/wv9bcz1ph5-delete-a-rule-in-ufw
