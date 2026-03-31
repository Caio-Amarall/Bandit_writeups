# Bandit level 30 → 31

## Objetivo
Repetindo novamente o mesmo objetivo, nos da
outro endereço e diz ser a mesma senha.

## Solução
Além das branchs e dos logs, ainda temos as tags.
Essa tag é como uma foto congelada do passado.

# Comandos usados
```bash
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
cd .\repo\
ls
git tag
git show secret
```

## Aprendizado

# Tags do git
Elas são usadas para marcar versões específicas (como "v1.0" ou "release-final").
Se a tag foi colocada em um momento em que a senha ainda existia, conseguimos
acessar ela.

## Conclusão
Após acessarmos a tag, conseguimos a senha.
Vamos para o próximo nível.
