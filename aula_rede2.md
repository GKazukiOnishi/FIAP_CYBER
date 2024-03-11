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
11. apt install net-tools
12. ifconfig
13. netstat -nltp
14. systemctl stop ssh
15. netstat -nltp
16. systemctl start ssh
17. systemctl stop ssh
18. systemctl stop apache2
19. netstat -nltp
20. Abrir D:\4SIS\Jaci Nunes\Kali Linux\kali-linux-2023.4-virtualbox-amd64
21. Iniciar a máquina e tirar snapshot também
22. Desligar a máquina
23. Configurar os adaptadores de rede igual à anterior
24. Iniciar máquina
25. User Senha -> kali kali
26. `sudo su` -> Senha kali
27. `ip -br -c a`
28. Seguir os passos:
```
cd /etc/network
cp interfaces interfaces.old
```
29. Configurar placa de rede que nem antes, usando na placa de rede 3 o eth2 e o endereço ip 192.168.1.20
30. Testar ping entre as máquinas

> init 0 -> desliga a máquina  
> init 6 -> reinicia  
> ssh -> porta 22  
> apache -> porta 80  
> service networking restart