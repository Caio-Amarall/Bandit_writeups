# Bandit level 26 → 27

## Objetivo
O level não nos da nenhuma informação diz apenas para
pegarmos a senha.

## Solução
Temos um arquivo com SETUID do level 27, precisamos usar ele
para pegar a senha no mesmo caminho que já fizemos outras vezes.

# Comandos usados
```bash
ls
./bandit27-do cat /etc/bandit_pass/bandit27
```
## Conclusão
Lendo o arquivo bandit27, temos a senha.
Vamos para próximo nivel.
