# Bandit level 14 → 15

## Objetivo
Temos que fazer uma conexão com localhost na porta 30000 para receber a senha.

## Solução
Devemos usar o nc para que ele faça uma ponte entre o localhost (meu computador)
e uma porta específica.

# Comandos usados
```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```
## Aprendizado

# O comando nc
Mais conhecido como NetCat, ele que faz a ponte entre o localhost
e outra porta específica.

## Conclusão
Após feita a conexão direta na porta 30000, recebemos a seguinte mensagem:
"Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo." Vamos para o próximo nível.
