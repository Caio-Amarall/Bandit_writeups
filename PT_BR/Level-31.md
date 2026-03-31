# Bandit level 31 → 32

## Objetivo
A mesma descrição dos niveís anteriores. Um endereço e a mesma senha
do nível 31.
## Solução
Agora em vez de buscar algo que foi apagado, precisamos enviar algo para o servidor.

# Comandos usados
```bash
"May I come in?" | Out-File -FilePath key.txt -Encoding ascii
git add key.txt
git commit -m "Agora em ASCII"
git push origin master
```
## Aprendizado

# Scripts automáticos
Se um atacante consegue permissão de escrita em um repositório, 
ele pode enviar um arquivo ou script que "engana" o servidor para executar comandos 
ou revelar segredos.

## Conclusão
Após lido o push, temos a senha para o penúltimo nível.
