# Bandit level 28 → 29

## Objetivo
Novamente a descrição deste nivel é um endereço git
e diz para usarmos a mesma senha do nivel 28.

## Solução
Devemos primeiramente, apagar o repositório que criamos
no nível anterior. Clonar ele novamente, só que agora
deste nível e investiga-lo. Lendo o arquivo clonado,
vemos que a senha está censurada. Para resolver isso,
precisamos acessar o histórico do arquivo e ver a senha
antes de ter sido alterada. Para remover o repositório, 
não conseguimos usar códigos por estarmos no Windows PowerShell,
então fazemos isso manualmente.

# Comandos usados
```bash
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
cd .\repo\
ls
git log -p
```
## Aprendizado

# Histórico do git
Mesmo feito alterações, as pastas ainda tem um histórico que mostra as informações
antes de serem alteradas. Devemos sempre explorar esse histórico.

## Conclusão
Depois de ver o histórico, temos a senha para o próximo nível.
