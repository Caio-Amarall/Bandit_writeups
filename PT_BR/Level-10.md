# Bandit level 9 → 10

## Objetivo
Precisamos usar um comando para ler o arquivo em binário e encontrar
dados imprimíveis, que estaram junto a senha. 

## Solução
Usaremos o comando String e logo após o grep para encontrar
o código que estará logo após um determinado caractér.

# Comandos usados
```bash
ls
strings data.txt | grep "=="
```
## Aprendizado

# O comando string
filtra apenas o que é "human-readable" (texto legível) dentro de um arquivo.

## Conclusão
Após encontrado, vamos direto para o próximo nível.
A senha é FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey.
