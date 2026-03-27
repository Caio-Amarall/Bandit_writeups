# Bandit level 19 → 20

## Objetivo
Temos que usar um setuid binário para conseguir a senha para o próximo nível.

## Solução
Sabemos o endereço do arquivo onde está a senha, logo só precisamo usar
o setuid para o ler.

# Comandos usados
```bash
ls -l
./bandit20-do ls /etc/bandit_pass
./bandit20-do cat /etc/bandit_pass/bandit20
```
## Aprendizado

# Comando Setuid
Normalmente, quando você executa um programa, ele roda com as suas permissões 
(bandit19). Um arquivo com a permissão SETUID roda com as permissões do dono 
do arquivo (neste caso, o bandit20).

## Conclusão
Após usar o setuid e ler o arquivo bandit20, temos a senha que procuravamos
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO. Vamos para próximo nível.
