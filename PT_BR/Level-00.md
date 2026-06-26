Bandit Level 0 → 1

Objetivo

Precisamos entrar no servidor do desafio usando SSH com as credenciais fornecidas.

Solução

Temos as seguintes informações:


Host: bandit.labs.overthewire.org
Porta: 2220
Usuário: bandit0
Senha: bandit0


Comandos usados

bashssh bandit0@bandit.labs.overthewire.org -p 2220

Aprendizado

Usamos o terminal para executar os comandos. Como estou usando o Windows,
utilizei o Windows PowerShell. É importante anotar isso pois podem surgir
diferenças em relação ao Linux nos próximos níveis.

SSH

O SSH é um programa que cria uma conexão segura com uma máquina remota e
permite executar comandos nela. A sintaxe usada foi:

ssh [usuario]@[servidor] -p [porta]

A opção -p especifica a porta a ser usada (padrão é 22; aqui usamos 2220).

Conclusão

Conectamos ao servidor usando o SSH. Vamos para o próximo nível!
