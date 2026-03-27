# Bandit level 20 → 21

## Objetivo
Temos que criar uma conexão localhost entre dois servidores para
usar o arquivo com setuid e descobrir a senha.

## Solução
Para descobrir como fazer isso, temos algumas opções. Uma delas
é rodar o comando sem nada: ./suconnect. Ele vai nos devolver:
./suconnect <port>, isso significa que precisamos conecta-lo
a uma port para que ele leia a senha e nos devolva outra.

# Comandos usados
```bash
ls -l
./suconnect
./suconnect 1234
```
em outro terminal
```bash
echo 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO | nc -l -p 1234 &
```

## Aprendizado

# Existência de variações de setuid
Ao colocar o comando vazio, descobrimos como ele funciona.

## Conclusão
Ao conectar-lo a uma port, temos a próxima senha.
