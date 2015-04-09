Syncthing on Kindle Touch
==========================

1. You need jailbreak and [KULA](http://www.mobileread.com/forums/showthread.php?t=203326) first.
2. Download this [repository]()
3. Download syncthing arm and copy syncthing to bin/
4. Connect Kindle Touch to Your PC
5. copy x to KINDLE-ROOT/extensions/syncthing
6. ssh into your kindle
7. Open firewall ports

```
# mntroot rw
# edit /etc/sysconfig/iptables
  -A INPUT -p tcp --dport 8080 -j ACCEPT
  -A INPUT -p tcp --dport 22000 -j ACCEPT
  -A INPUT -p udp --dport 21025 -j ACCEPT
# iptables-restore < /etc/iptabels/iptables.rules
# mnroot ro
```
8. Start syncthing for the first time, generate private key, ...

```
# /mnt/us/extensions/syncthing/bin/syncthing -home=/mnt/us/extensions/syncthing/config
# edit /mnt/us/extensions/syncthing/config/config.xml, so that you can access the web GUI from other computers
  <gui enabled="true" tls="false">
     <address>0.0.0.0:8080</address>
```
