Setup Syncthing on Kindle Touch
==========================

1. You need jailbreak and [KULA](http://www.mobileread.com/forums/showthread.php?t=203326) first.
1. Download this [repository](https://github.com/gutenye/syncthing-kindle/archive/master.zip)
1. Download [syncthing-linux-arm](https://github.com/syncthing/syncthing/releases) and copy `syncthing` binary to `syncthing/bin/`
1. Connect Kindle Touch to Your PC
1. Copy `syncthing/` to `KINDLE-ROOT/extensions/syncthing/`
1. Select "Open Firewall for Kindle" from KUAL
1. Select "Start Syncthing INSECURE Admin" from KUAL
1. Find out your Kindle IP address by type `;711` in search, then open `http://IP-ADDRESS:8080` in your browser. <br>
1. Configure all peers and folders
1. Ignore kindle auto generated index files: `*.sdr`
1. Select "Close INSECURE Admin port" from KUAL
1. Select "Stop Syncthing" and then "Start Syncthing" from KUAL
1. Note: connect kindle to computer or restart kindle will terminate syncthing process and firewall.
