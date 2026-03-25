# Bandit level 6 → 7

## Objetivo
Precisamos encontrar o arquivo em todo o diretório raiz, não sabemos
qual o diretório certo e nem o nome do arquivo. Temos algumas
propriedades: user bandit7, group bandit6 e tamanho 33 bytes.

## Solução
Com as propriedades mencionadas, devemos usar o find para procurar
em todo o diretório raiz. E logo após, usar as opções para especificar
as propriedades.

# Comandos usados
```bash
find / -user bandit7 -group bandit6 -size 33c
cat /var/lib/dpkg/info/bandit7.password
```

## Aprendizado

# Usar find no diretório raiz
Utilizamos a "/" para dizer que queremos que o find funcione no diretório
raiz, não apenas no diretório em que estamos localizados.

# Novas opções do find
A opção "-user" é feita para procurar por um usuário dono do arquivo.
A opção "-group" busca arquivos pertecentes a um grupo.

## Conclusão
Lemos o arquivo bandit7.password, então adquirimos a senha.
Vamos para o próximo nível.
