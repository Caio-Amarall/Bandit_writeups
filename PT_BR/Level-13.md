# Bandit level 12 → 13

## Objetivo
Esse foi bem trabalhoso, precisamos criar um diretório /tmp,
copiar o arquivo para dentro dele, usar o file no arquivo para
identificar o tipo dele, usar o xxd para descriptografar ele do
hexadecimal, ficar identificando o tipo do arquivo e por fim,
ficar descriptografando ele repetidas vezes.

## Solução
Após criar um diretório, copiar o arquivo, descobrir o tipo de arquivo
usar diversos comando repetidas vezes, encontramos o arquivo certo.

# Comandos usados
```bash
mkdir /tmp/Desafio_bandit12
cp data.txt /tmp/Desafio_bandit12
cd /tmp/Desafio_bandit12
xxd -r data.txt > data.bin
file data.bin
mv data.bin data.gz
gunzip data.gz
file data
mv data data.bz2
bzip2 -d data.bz2
file data
mv data data.tar
tar -xf data.tar
file data.bin
```
e assim repetidamente até encontrar o arquivo certo...
O arquivo que procuramos terá ASCII como tipagem.
## Aprendizado

# Comando mkdir
Ele serve exclusivamente para criar pastas.

# Comando xxd
cria ou lê arquivos hexadecimais.

# O paramêtro -r
O -r (Reverse) faz o contrário: pega aquele texto cheio de 
números e transforma de volta em um arquivo "real" (binário).

# Comando mv
Renomeia os arquivos.

# Comando gunzip
Descompacta arquivos no formato .gz.

# Comando bzip2
Descompacta arquivos no formato .bz2. O -d serve para
descompactar.

# Comando tar
Descompacta arquivos no formato POSIX. Os paramêtros
-xf serve para extrair e indicar o arquivo que esta sendo usado.

## Conclusão
Depois de um longo processo de descompactação, conseguimos chegar no
arquivo que queremos e ele nos entrega a senha: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn.




