# Bandit level 18 → 19

## Objetivo
Temos que ler o arquivo readme e então teremos a senha.

## Solução
Precisamos colocar um comando junto ao ssh de entrada,
já que quando efetuamos a entrada, o .bash alterado nos
expulsa imediatamente. Dessa forma, vamos ler o arquivo
antes mesmo de entrar no servidor e teremos a senha.

# Comandos usados
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```
## Aprendizado

# Podemos colocar um comando dentro do comando ssh
Podemos colocar as aspas duplas para inserir um comando
antes mesmo de efetuar a entrada no servidor. Assim que
entrarmos, ele efetua o comando e temos a resposta.

## Conclusão
Conseguimos a senha: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8.
vamos para próximo nível!
