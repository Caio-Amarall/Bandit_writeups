# Bandit level 27 → 28

## Objetivo
A descrição do nível nos da apenas um caminho: 
ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo via the port 2220
e nos diz para usar a senha do level 27.

## Solução
Com essas informações, teremos de usar um git clone para
conseguir clona-lo para o seu computador nativo e então
conseguir ler o arquivo.

# Comandos usados
```bash
git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
cd repo
ls
cat .\README
```
## Aprendizado

# Repositório GIT
o Git funciona como uma biblioteca remota. Desenvolvedores usam 
o Git para salvar versões do código, e muitas vezes "esquecem" senhas 
ou chaves em versões antigas.

## Conclusão
Após ler o arquivo criado .\README, conseguimos a senha
para o próximo nível. Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN.
