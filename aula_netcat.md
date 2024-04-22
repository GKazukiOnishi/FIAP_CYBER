# Netcat
0. No Debian
1. `apt update`
2. `apt install netcat`
3. Netcat - Canivete Suiço de redes, ajuda a trabalhar com protocolo DHCP e diversos outros. Sabe manipular documentos, portas etc.
4. `man netcat`
5. LTVP - Listen | Time | Verbose | Port - As letras que vamos usar do netcat
6. No Debian - `python3 -m http.server 8080`
7. No Kali - `nc -v 192.168.1.10 8080`
8. O comando acima abre a conexão na 8080, e no Debian ele vai estar esperando as requisições http
9. Esteganografia - Esconder mensagem usando um tipo de tinta, que quando joga limão aparece
10. Espiões hoje em dia usam, isso pode ser em sites com informações criptografadas
11. `nc -v 192.168.1.10 8080` e depois que carrega digitamos: `GET / HTTP/1.1` - Pode ser o ip 10.20.23.11 também (IP do bridge do servidor)
12. Com isso a requisição vai ser enviada e vai retornar o GET do servidor para nós
13. Podemos fazer o mesmo subindo apache2 no Servidor e testando na porta 80 -> Vai dar bad request, porque ele não aceita a requisição
14. Como usar técnica de esteganografia para burlar o servidor e obter informações?
15. Perceba que podemos mandar uma requisição POST para o python, e vai dar 501 - Not Implemented
16. Perceba que mandando para o apache2 temos um 400
17. `printf "OPTIONS / HTTP/1.1\r\n\r\n"` -> \r\n é equivalente a um Enter
18. Fazendo isso, enviamos a requisição já sem avisar o servidor
19. `printf "OPTIONS / HTTP/1.0\r\n\r\n" | nc 192.168.1.10 80` -> vai dar 200 -> atenção que estamos usando a versão 1.0
20. Podemos fazer isso para qualquer método HTTP

* Obs: Podemos mudar o keyboard layout do Kali Linux para o idioma pt-br