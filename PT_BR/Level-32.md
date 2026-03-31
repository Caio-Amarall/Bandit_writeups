# Bandit level 32 → 33

## Objetivo
A descrição do nível nos da boa sorte e diz para escaparmos.

## Solução
Ao entrar no servidor do nível 32, nos vemos numa prisão.
Não conseguimos usar nenhum código pois há um script que 
deixa tudo que é digitado em MAIÚSCULO. Dessa forma, 
o terminal não lê os códigos pois é sensivel a letras
maiúsculas e minúsculas, isso significa que códigos
como: ls, cat, cd... só funcionam em minúsculo. Não
existe os códigos em maiúsculo sendo assim são dados
como erros.

# Comandos usados
```bash
$0
cat /etc/bandit_pass/bandit33
```
## Aprendizado

# $0
Variável que representa o nome do shell ou programa atual 
(usada para escapar de shells restritos).

## Conclusão
E assim, finalizamos todos os desafios de bandit.
