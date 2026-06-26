# Bandit level 15 → 16

## Objetivo
Precisamos nos conectar ao localhost na porta 30001 usando SSL/TLS e enviar
a senha do nível atual para receber a senha do próximo nível.

## Solução
O comando `nc` (Netcat) não consegue lidar com conexões SSL. Precisamos usar
o `openssl s_client`, que funciona como um cliente SSL/TLS capaz de se
comunicar com serviços criptografados. Conectamos ao servidor, enviamos a
senha atual e recebemos a próxima.

## Comandos usados
```bash
openssl s_client -connect localhost:30001
```
## Aprendizado

## O comando substituto do nc
Funciona como um "Netcat com esteroides" que consegue 
conversar com serviços protegidos por certificados.

## Conclusão
Após concluir a conexão, colocamos a senha que usamos
para entrar no servidor 15 e conseguimos a senha.
vamos para o próximo nível!
