# Bandit level 25 → 26

## Objetivo
Salvar a chave .sshkey e encontrar uma forma de permanecer conectado ao servidor.

## Solução
Nós temos que diminuir a janela o suficiente para que apareça um "--more--"
para que assim, não sejamos expulso do servidor. Se for feito no 
Windows PowerShell, temos que usar o comando cntrl + para as letras
ficarem grandes o suficiente para que o texto não caiba inteiro.

# Comandos usados
```bash
cntrl + (10x)
ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220
v
:set shell=/bin/bash
:shell
```
## Aprendizado

# Escape de interface
Muitos sistemas (caixas eletrônicos, totens de aeroporto, servidores restritos) 
rodam um programa por cima do Windows ou Linux. Se você conseguir "travar" 
esse programa em um modo de erro ou visualização, você pode usar atalhos ocultos 
para chamar o sistema operacional que está por trás.

## Conclusão
Após garantido o acesso, já estamos dentro do próximo nível.
