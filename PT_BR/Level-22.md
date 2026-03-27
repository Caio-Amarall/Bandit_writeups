# Bandit level 21 → 22

## Objetivo
Temos que ir até a pasta /etc/cron.d/ e investigar como conseguir
a senha para o próximo nível.

## Solução
Após ler o arquivo cronjob_bandit22, ele nos da um comando que
diz exatamente como ele funciona. Investigando o comando
descobrimos outro caminho do script, lendo o script
nos é informado que ele cria uma pasta temporária para guardar
informações, lendo ele descobrimos a senha.

# Comandos usados
```bash
ls -l
cd /etc/cron.d/
ls -la
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
## Aprendizado

# Pasta temporária
Alguns aplicativos criam pastas temporárias para guardar
informações, se estas pastas não forem configuradas da
forma correta, qualquer um poderá as ler.

## Conclusão
Após ler a pasta tmp, temos a senha do próximo nível.
