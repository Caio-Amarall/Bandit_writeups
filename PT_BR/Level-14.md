# Bandit level 13 → 14

## Objetivo
Precisamos ler o arquivo em um determinado caminho porem
apenas o usuario bandit14 consegue o ler.

## Solução
Para isso, devemos trazer a chave privada para nosso computador
e se conectar daqui.

# Comandos usados
```bash
cat sshkey.private
nano bandit14.key
ssh -i bandit14.key bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14
```
aqui eu tenho que explicar algumas coisas, encontramos o problema
que eu havia citado la no Level-01.md. Por usar o terminal PowerShell
do windows, o comando chmod não funciona como deveria. Então devemos
entrar nas propriedades do arquivo manualmente e alterar as permissões
dele para que sejamos o único usuário a conseguir ler e usar.

## Aprendizado

# O parâmetro -i
Significa identify file diz ao SSH para usar o arquivo mencionado 
como sua "chave" de entrada.

# O comando nano
Cria um arquivo no seu computador.

## Conclusão
Após isso, o arquivo bandit14 nos da a seguinte senha:
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS.
