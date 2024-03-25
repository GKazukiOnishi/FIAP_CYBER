# Segurança em Apache2

1. Arquivo de config do apache em /etc/apache2/apache2.conf
2. Fazemos uma cópia para ter um bkp
3. `cp apache2.conf apache2.conf.old`
4. Mover o /var/www/html/index.html para o /var/www
5. `service apache2 restart`
6. Verificar se o index abre ou não -> Podemos ver as pastas
7. nano apache2.conf -> Removemos a palavra Indexes de uma tag Directory lá em baixo
8. Isso tira o acesso às pastas do servidor
9. Colocamos de volta
10. nano etc/apache2/conf-enabled/security.conf
11. ServerTokens -> Configuração em que definimos o que podem descobrir do servidor
12. Mudamos para modo PROD -> O sistema Operacional não fala mais
13. Restart do apache2
14. Voltamos para ServerTokens OS
15. Restart do apache2
16. ServerSignature Off -> Assinatura do Servidor
17. Restart
18. Some tudo, porque? Porque ele apaga o banner do servidor
19. em /var/log/apache2 -> arquivo access.log contém todos os logs do apache2
20. Comandos 
```
cat access.log | wc -l
cat /etc/passwd -> usuários do linux
tail /etc/passwd -> 10 últimas linhas
head /etc/passwd -> 10 primeiras linhas
tail -n 4 /etc/passwd -> 4 últimas linhas
cat /etc/passwd | wc -l -> total de linhas no arquivo (ou seja, total de users)
```
21. No access.log podemos ver várias coisas úteis: Método HTTP, código da response, porta, navegador, arquitetura etc.