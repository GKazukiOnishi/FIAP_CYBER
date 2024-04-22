# Configurando a interface Bridge
Para configurar basta utilizar o interfaces novamente, mas configurando o adapter referente ao bridge, usando o mesmo IP da sua máquina física.
1. Configuramos a interface em `nano /etc/network/interfaces`
2. "allow-hotplug eth2 iface eth2 inet static address 10.20.23.11"
3. Fazemos isso no Debian e no Kali
4. Para testar entramos em uma das máquinas e damos ping em outra, tipo 10.20.23.12.
5. Subimos um servidor python no Debian: `python3 -m http.server 8080`
6. Perceba que outras máquinas da fiap conseguem acessar o nosso servidor através do nosso ip 10.20.23.11