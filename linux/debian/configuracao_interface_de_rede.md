# Arquivo de exemplo de configuração de interface de rede Debian GNU/Linux 11 (bullseye)

Edite o arquivo `/etc/network/interfaces` e adeque-o ao seu ambiente.

```
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# ifup automatic
auto ens33

# Restarts the network when the Lan cable is connected
allow-hotplug ens33

# add dhcp seettings
#iface enp1s0 inet dhcp

# add static settings
iface ens33 inet static

# IP address
address 192.168.196.250

# subnet mask
netmask 255.255.255.0

# default gateway
gateway 192.168.196.2

# name server
dns-nameservers 8.8.8.8 8.8.4.4
```

Referências:  
https://www.server-world.info/en/note?os=Debian_11&p=initial_conf&f=3  
https://www.lest5.com.br/lest/index.php/redes/comandos-redes/configurar-uma-rede-linux-via-terminal
