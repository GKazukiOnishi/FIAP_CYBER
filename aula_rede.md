# Rede

nano /etc/network/interfaces  
  
Configurar VM para adicionar rede interna  
  
nano /etc/network/interfaces  

adicionar
allow-hotplug enp0s8
iface enp0s8 inet static
        address 192.168.1.10

