# Bandit level 8 → 9

## Objetivo
Precisamos ler o arquivo data.txt e encontrar o código entre varios outros.

## Solução
Temos que usar o comando "sort" para que ele coloque tudo em ordem alfabética
e o comando "uniq -u" para especificar que apenas aparece uma única vez
# Comandos usados
```bash
ls
sort data.txt | uniq -u
```
## Aprendizado

# O comando sort
coloca o arquivo em ordem alfabética, agrupando as repetidas.

# O comando uniq
só funciona se as linhas repetidas estiverem uma ao lado da outra. Por isso,
usamos o código sort antes deste.

# O caractér |
Chamado de "Pipe" pega o resultado do primeiro comando e joga para o próximo
comando. Serve para agilizar e colocar na mesma linha.

# O paramêtro -u
Este paramêtro diz para o comando que queremos apenas a linha que aparece
uma única vez.

## Conclusão
Após isso, adquirimos o código e vamos para o próximo nível.
