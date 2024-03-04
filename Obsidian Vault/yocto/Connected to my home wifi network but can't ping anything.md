

https://bbs.archlinux.org/viewtopic.php?id=259362

For one thing, I have installed fresh Archlinux many times to several laptops and desktops since I met with it in 2016. Never I had to configure NetworkManager other than to start its unit service (NetworkManager.service).

However because of this recent issue I run into, I did have to get my feet wet with NM's configuration.  But so far I did not change much. Because I mean, I don't believe there is anything to do with configuration.

Here are some more outputs:

```
cat /etc/NetworkManager/conf.d/dhcp-client.conf
```

```
cat /etc/NetworkManager/conf.d/dns.conf

[main]
dns=none
systemd-resolved=false
```

```
cat /etc/NetworkManager/NetworkManager.conf

# Configuration file for NetworkManager.
# See "man 5 NetworkManager.conf" for details.
```

```
cat /etc/hosts

# Static table lookup for hostnames.
# See hosts(5) for details.
127.0.0.1 localhost
::1 localhost
127.0.1.1 MyComputer.localdomain MyComputer
```

```
cat /etc/hostname 
MyComputer
```

My computer's hostname is actually "MyComputer", it is not an edit ![smile](https://bbs.archlinux.org/img/smilies/smile.png)



