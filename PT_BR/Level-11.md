# Bandit level 10 → 11

## Objetivo
Precisamos ler o arquivo data.txt que está criptografado com base64.

## Solução
Usaremos o próprio código base64 para descriptografar e ler o arquivo
encontrando assim a senha para o próximo nível.

# Comandos usados
```bash
ls
base64 -d data.txt
```

## Aprendizado

# O código base64
É um código do linux para manipular essa codificação.

# O paramêtro -d
Abreviação de decode. Ele pega aquele "texto estranho" 
(cheio de letras maiúsculas, minúsculas e números) e o transforma de 
volta em texto legível (human-readable).

## Conclusão
Após decodificar, encontramos a senha para o próximo nível.
A senha é dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr.
