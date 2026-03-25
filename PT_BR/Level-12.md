# Bandit level 11 → 12

## Objetivo
Precisamos ler o arquivo data.txt que está criptografado com Cifra de César
em 13 letras.

## Solução
Temos que usar o código tr para decodificar a cifra de césar.

# Comandos usados
```bash
ls
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
## Aprendizado

# O comando tr
O tr faz o mapeamento, ele troca as letras por outras, deve
ser especificado quais as letras.

# O paramêtro 'N-ZA-Mn-za-m'
Este paramêtro diz que o alfabeto deve começar pelo N, ir
até o Z e recomeçar no A até o M.

## Conclusão
Após feita a decodificação, temos a senha
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4.
