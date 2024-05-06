# Aula NETCAT parte 2
1. Para funcionar a conexão via BRIDGE, precisamos desligar a interface de rede interna!
2. Esteganografia - Técnica de ocultar mensagens
    * Ex: Publicar foto na rede social, que parece uma simples foto comum, mas para algum espião, ele consegue ler a mensagem escondida
    * Os arquivos contém hash, propriedades, dados, que indicam a sua origem, permitindo identificar quando copiaram arquivos
3. Vamos usar o comando `printf "OPTIONS / HTTP/1.0\r\n\r\n" | nc -v 10.20.23.11 80` para acessar os métodos disponíveis do Apache, coisa que não é possível fazendo uma requisição simples com o `nc -v 10.20.23.11 80` e escrevendo após `OPTIONS / HTTP/1.0`
4. Com o printf conseguimos ver os métodos HTTP disponíveis, sem ele não, apenas tomamos um 400
5. Agora no servidor python, tomamos o erro 501 (Unsupported Method) independente do comando.
6. Por que o printf funciona? Porque ele burla a conexão com o servidor que ocorre ao apertarmos um Enter no comando nc -v. No caso do printf ele faz isso tudo de uma vez e acaba burlando o apache2.