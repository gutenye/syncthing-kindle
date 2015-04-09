Syncthing on Kindle Touch
==========================

1. You need jailbreak and [KULA](http://www.mobileread.com/forums/showthread.php?t=203326) first.
2. Download this [repository](https://github.com/gutenye/syncthing-kindle/archive/master.zip)
3. Download [syncthing-linux-arm](https://github.com/syncthing/syncthing/releases) and copy `syncthing` binary to `bin/`
4. Connect Kindle Touch to Your PC
5. copy the folder to KINDLE-ROOT/extensions/syncthing
6. ssh into your kindle
7. Open [firewall ports](https://github.com/syncthing/syncthing/wiki/Firewalls-and-Port-Forwards#local-firewall)

```
# mntroot rw
# edit /etc/sysconfig/iptables
  -A INPUT -p tcp --dport 8080 -j ACCEPT
  -A INPUT -p tcp --dport 22000 -j ACCEPT
  -A INPUT -p udp --dport 21025 -j ACCEPT
# iptables-restore < /etc/sysconfig/iptables.rules
# mnroot ro
```
8. Start syncthing for the first time, and enable [access the web GUI from other computers](https://github.com/syncthing/syncthing/wiki/Firewalls-and-Port-Forwards#remote-web-gui)

```
# /mnt/us/extensions/syncthing/bin/syncthing -home=/mnt/us/extensions/syncthing/config
# edit /mnt/us/extensions/syncthing/config/config.xml
  <gui enabled="true" tls="false">
     <address>0.0.0.0:8080</address>
```
9. Ignore kindle auto generated index files on SYNC-FOLDER

```
$ edit SYNC-FOLDER/.stignore on both device, or use a global ignore file
  *.sdr
```
