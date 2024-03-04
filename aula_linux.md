# Comandos para Inspecionar sistema

ip -br -c a  
whoami  
  
last -> últimos logins  
last | less  

passwd aluno -> muda senha do user aluno  
hostname  

uname -a -> kernel  

pwd -> a pasta em que você está  
ls  

ls -a -> tudo  
ls -d -> só os que não estão ocultos  
  
## Caracteres coringas:  
* '*' -> tudo em qualquer quantidade -> `ls -l /dev/sda*`  
* '?' -> Um único caractere qualquer -> `ls -l /dev/sda?`  
* '[]' -> Intervalo de caracteres -> `ls -l /dev/tty[1-9]`  
* '{}' -> Gama de expressões -> `ls -l /dev/tty{1,2,4}`  
  
mkdir -m 777 nomeDiretorio -> criar pasta com permissão 777  
touch nomeFile -> cria arquivo  
rm -d nomeDiretorio -> apagar diretório  
  
nano arq.txt -> editor de texto -> usamos Ctrl + tecla para fazer ações  
  
cat arq.txt -> mostra o que tem no arquivo  

  
