# Bandit level 5 → 6

## Objetivo
Agora precisamos encontrar uma pasta especifica em algum lugar do diretório 
inhere, que segue as seguintes propriedades: legível, 1033 de tamanho e não executável.

## Solução
Temos a localização base da pasta e as propriedades.

# Comandos usados
```bash
ls
cd inhere/
ls -la
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```
## Aprendizado

# Opções do find
Para identificarmos um arquivo com mais de uma propriedade, precisamos
utilizar as opções de find. -type é a opção que especifica o tipo do
arquivo, -size especifica o tamanho do arquivo e o "c" diz em quantos
bytes. A "!" significa 'not', ou seja, isso quer dizer que ele inverte
o próximo comando, que era -executable, logo não executável.

## Conclusão
Após lermos o arquivo encontrado encontramos mais um código.
A senha encontrada é HWasnPhtq9AVKe0dmk45nxy20cvUa6EG.
