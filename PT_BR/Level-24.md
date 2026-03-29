# Bandit level 24 → 25

## Objetivo
O level nos diz que tem um script rodando procurando 
pela senha do level 24 + um PIN de 4 digitos.

## Solução
Criaremos um script bruto para que ele envie a senha e teste
todas as combinações de PIN possiveis (0000..9999).

# Comandos usados
```bash
cd /tmp/meu_hack
nano brute.sh
#!/bin/bash
# Substitua SENHA_B24 pela senha real que você pegou no nível anterior
senha="SENHA_B24"

for i in {0000..9999}; do
    echo "$senha $i"
done
chmod +x brute.sh
./brute.sh | nc localhost 30002
```
## Aprendizado

# Automação
Se eu levar 5 segundos para digitar cada um dos 4 digitos PIN, 
vou demorar 14 horas sem parar. Se eu fizer um script, 
o computador testa tudo em 30 segundos. O custo-benefício da automação é óbvio.

## Conclusão
Após criarmos a automação, ela nos da a senha para o próximo nivel.
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4.
