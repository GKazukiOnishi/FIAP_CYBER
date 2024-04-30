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
21. Como montar um chat entre duas máquinas conectadas em rede?
22. `nc -lvp 1234` -> Abre uma porta com o netcat escutando
23. `nc -v 192.168.1.10 1234` -> Abre uma conexão com o IP 192.168.1.10 na porta 1234
24. Com isso a máquina que rodou o segundo comando consegue enviar mensagens para a outra
25. Obs: Não é full-duplex, só envia de um lado. Mas você pode fazer o inverso entre as máquinas e aí a outra vai poder enviar mensagem
26. `md5sum arquivo` -> Gera um hash desse arquivo usando md5
27. `sha256sum arquivo` -> Gera um hash desse arquivo usando sha256 -> maior que o md5
28. Hashs são úteis para identificar arquivos iguais, ao alterar qualquer coisa do arquivo o hash já muda. Obs: Ele é único por conteúdo de arquivo
29. Isso permite identificar arquivos copiados, arquivos sendo enviados via net etc.
30. Ex: Nudes que precisam ser retirados da internet podem ser identificados assim. Mas se alguém tira print e mexe, por exemplo, não dá para saber a não ser que pegue o hash desse print.
31. O ideal é avisar o Meta sobre essa foto com o hash, e a polícia
32. Randomwares -> Sequestram informações e para enviarem elas de volta cobram um valor alto. Mas como que pegam esses dados? Como enviar arquivos?
33. Como confiar se o arquivo realmente foi enviado sem perda de dados? Usamos o hash!
34. Para enviar: No servidor rodamos: `cat arquivo123 | nv -lvp 1234` -> Vai disponibilizar o arquivo na porta 1234
35. Na Outra maquina que quiser ver o arquivo: `nc -v 192.168.1.10 1234 > arquivo123` -> Vai pegar os bytes do arquivo pela rede e jogar no arquivo1234
36. Podemos entao verificar o hash dos arquivos para garantir que sao a mesma coisa

* Obs: Podemos mudar o keyboard layout do Kali Linux para o idioma pt-br