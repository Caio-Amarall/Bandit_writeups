# Bandit level 16 → 17

## Objetivo
Agora temos que encontrar a porta certa dentre uma grande margem
31000-32000. Após encontrada, devemos conectar a ela, inserir a senha
que já sabemos e finalmente conseguir um jeito de entrar no nível 17.

## Solução
Para encontrar a porta certa, devemos usar o comando nmap.
Após isso, usamos o comando aprendido no último nível para 
conectar a porta certa. Depois, não recebemos a senha como normalmente
recebemos uma chave privada igual ao nível 14. Fazemos o mesmo
procedimento, criando uma chave em nosso computador, alterando 
as permissões e donos do arquivo. E finalmente, usando ele como
a senha para entrar.

# Comandos usados
```bash
nmap -p 31000-32000 localhost
openssl s_client -connect localhost:31790
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
exit
ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
```
## Aprendizado

# O comando nmap
É a ferramenta padrão da indústria para descobrir dispositivos, portas
e serviços em uma rede.

## Conclusão
Agora, já estamos dentro do próximmo nível.
