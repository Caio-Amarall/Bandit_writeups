# Bandit level 22 → 23

## Objetivo
Temos que ir até a pasta /etc/cron.d/ e investigar o script do cron para
descobrir como obter a senha do próximo nível.

## Solução
Lendo o script do cron, descobrimos que ele usa o nome do usuário atual para
gerar um hash MD5. Esse hash é usado como nome de um arquivo temporário em /tmp
que contém a senha. Precisamos calcular o hash para o usuário `bandit23` e
ler o arquivo correspondente.

## Comandos usados
```bash
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
cat /tmp/<hash_obtido>
```

## Aprendizado

## md5sum
O `md5sum` gera um hash de 32 caracteres a partir de qualquer entrada de texto.
É amplamente usado para verificar integridade de arquivos, mas **não deve ser
usado para armazenar senhas**, pois é rápido demais e vulnerável a ataques de
dicionário e rainbow tables.

## Como o script funciona
```bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
Substituindo `$myname` por `bandit23`, calculamos o mesmo hash e encontramos
o arquivo com a senha.

## Conclusão
Simulando a lógica do script para o usuário `bandit23`, calculamos o hash MD5
correto e conseguimos ler o arquivo temporário com a senha do próximo nível.
