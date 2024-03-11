# Aprendendo a configurar redes no linux

1. Iniciamos a máquina virtual (pasta 4SIS - D:\4SIS\Jaci Nunes\SERVIDOR DHCP\vm2 1)
2. Criamos snapshot da imagem linux usando como nome a data, referenciando o início da aula
3. Poweroff
4. Configuramos os adaptadores de rede para ter uma em Bridge e outra em rede interna da fiap
5. Iniciarmos a máquina
6. Copiamos o arquivo /etc/network/interfaces para ter um backup `cp /etc/network/interfaces /etc/network/interfaces.old`
7. `nano /etc/network/interfaces`
8. Configuramos então as outras placas de rede
    * Adicionamos a seguinte linha de código:
```
# placa de rede 2 - bridge

# placa de rede 3 - interna
allow-hotplug enp0s9
iface enp0s9 inet static 
      address 192.168.1.10
```
9. apt update
10. apt install apache2

> init 0 -> desliga a máquina  
> init 6 -> reinicia 