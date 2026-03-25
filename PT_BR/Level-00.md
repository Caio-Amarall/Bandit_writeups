# Bandit Level 0 

## Objetivo
Preciso entrar no servidor HOST do desafio usando o SSH.

## Solução
Temos as seguintes informações:
Ip: bandit.labs.overthewire.org
Port: 2220
Login: bandit0
Senha: bandit0

# Comandos usados
```bash
ssh bandit0@bandit.overthewire.org -p 2220
bandit0
```
## Aprendizado
Usamos o terminal para colocar os códigos, cada SO tem um terminal diferente.
Como estou usando o Windows, usarei o Terminal Windows PowerShell. É bom
deixar especificado pois aparecerão problemas futuros.

# SSH
O ssh é um programa que faz conexão em uma maquina remota e executa comandos
nessa maquina. Foi usado da seguinte forma: ssh "[usuario]@{servidor} (opções)"
-p é uma opção para o SSH, serve para especificar a port usada.

## Conclusão
Conectamos ao servidor usando o SSH, vamos para o próximo nivel.

