# Bandit level 29 → 30

## Objetivo
Este nível se assemelha aos dois últimos, nos dando a mesma descrição,
um endereço e diz ser a mesma senha do nível 29.

## Solução
Novamente, devemos remover a pasta repo que clonamos no ultimo nível.
Dessa vez, o histórico não nos mostrará nada, temos que acessar as
branchs do git para descobrir um novo galho. Acessando um deles
temos um histórico interno, com a senha.

# Comandos usados
```bash
git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
cd .\repo\
git branch -a
git checkout removes/origin/dev
cat .\README.md
```
## Aprendizado

# Branch do git
diferente, do histórico que usamos no nível anterior, temos ainda
a branch que é onde os programadores costumam deixar "sujeira", 
testes e, infelizmente, senhas reais antes de limparem o código para a versão final.

## Conclusão
acessando a branch, lendo o arquivo temos a senha.
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL.
