# Aula de Redes - Parte 3

1. Iniciar máquina virtual debian (192.18.1.10)
2. Iniciar máquina virtual Kali Linux (192.18.1.20)
3. `ip -br -c a` nas duas máquinas para verificar ip
4. `netstat -nltp` na máquina debian para verificar serviço apache2 ligado
5. Na máquina Kali acessar 192.168.1.10 no Mozilla para ver a página index.html do apache2
6. `service apache2 stop` na máquina debian
7. Recarregar página do apache no Kali para verificar que não tem mais (Ctrl + Shift + R para limpar cache)
8. `service apache2 start` na máquina debian para reiniciar o serviço
9. Testar tela de novo
10. na máquina debian ir para `cd /var/www/html`
11. Verificar existência do arquivo `index.html`
12. `service apache2 stop`
12. Mover index.html para uma pasta antes `mv index.html ../`
13. `service apache2 start`
14. Perceber que a página muda e começa a mostrar várias informações sensíveis para possíveis invasores, como a versão do apache, máquina, ip etc.
15. Por isso nunca devemos mover o arquivo padrão de um servidor, porque tirando você pode correr o risco de expor várias informaçõs do servidor
16. Criar um novo index.html na pasta /var/www/html: `nano index.html` e colocar qualquer texto
17. Acessar na máquina Kali para ver que mudou o index.html
18. Com isso não vamos mais poder ver a versão, servidor e etc.. Ainda é possível acessar as pastas e arquivos, porém essas informações já não vão mais ficar expostas facilmente.
19. Pesquisando Apache2 2.4 exploit podemos encontrar várias vulnerabilidade só sabendo da versão e servidor
20. Pesquisar Type of Apache
21. Pesquisar shodan.io: Site que permite encontrar qualquer dispositivo conectado à internet
22. Criar arquivo na pasta /home/aluno
23. Na máquina debian `python3 -m http.server 8080`
24. Na máquina Kali acessar 192.168.1.10:8080 -> vamos enxergar os arquivos criados em /home/aluno
25. Criar arquivo index.html para esconder arquivos e iniciar servidor de novo
26. 

> `> arquivo.txt`: Cria arquivo  
> `echo "texto qualquer" > arquivo.txt`: Adiciona texto no arquivo  
> `echo "outro texto" >> arquivo.txt`: Adiciona no final do arquivo outro texto  