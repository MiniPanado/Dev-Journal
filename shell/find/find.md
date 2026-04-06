# find

## O que é
find é um comando usado para procurar arquivos e diretórios dentro do sistema de arquivos com base em vários critérios (nome, tipo, tamanho, data, permissões, etc.).

## Para que serve
Serve para localizar arquivos rapidamente, automatizar tarefas, limpar arquivos antigos, buscar por padrões específicos e executar comandos nos resultados encontrados.

## Como usar
find [caminho] [opções] [expressão]

## Exemplos

### Procurar um arquivo pelo nome
find . -name "file.txt"

### Procurar sem diferenciar maiúsculas/minúsculas
find . -iname "file.txt"

### Procurar apenas diretórios
find . -type d

### Procurar apenas arquivos
find . -type f

### Procurar por extensão
find . -name "*.js"

### Procurar arquivos maiores que um tamanho
find . -size +10M

### Procurar arquivos menores que um tamanho
find . -size -1k

### Procurar arquivos modificados recentemente
find . -mtime -1

### Procurar e apagar arquivos
find . -name "*.log" -delete

### Procurar e executar comando
find . -name "*.js" -exec rm {} \;

### Procurar arquivos vazios
find . -empty

### Limitar profundidade da busca
find . -maxdepth 2 -name "*.txt"

### Usar expressões regulares (ver regex.md)
find . -regex ".*\.js"

## Flags úteis

### Procurar por nome
-name

### Procurar por nome sem case-sensitive
-iname

### Procurar por apenas arquivos
-type f

### Procurar por apenas diretórios
-type d

### Filtrar por tamanho
-size

### Filtrar por data de modificação
-mtime

### Limitar profundidade
-maxdepth

### Procurar por arquivos ou diretórios vazios
-empty

### Apagar diretamente
-delete

### Executar comando nos resultados
-exec

### Combinações comuns
- find . -name "*.log" -delete → procurar arquivos .log e apagar
- find . -type f -size +100M → procurar arquivos grandes
- find . -name "*.txt" -exec mv {} backup/ \; → procurar e mover arquivos
- find . -mtime +7 -delete → procurar arquivos antigos e apagar

## Notas

- find procura recursivamente por padrão (não precisa de -r).
- Pode ser pesado em diretórios grandes → use -maxdepth para limitar.
- -delete é poderoso — use com cuidado.
- -exec é muito útil, mas pode ser mais lento que usar xargs em alguns casos.

## Conceitos importantes

### Caminho (.)
- . → diretório atual
- / → raiz do sistema
- ~/ → home do usuário

### Expressões
#### O find usa expressões para filtrar resultados:
- -name "*.js"
- -type f
- -size +10M

### {} no -exec
- Representa o arquivo encontrado.

### \; no -exec
- Indica o fim do comando executado.

### Unidades
- c → bytes
- k → KB
- M → MB
- G → GB

### Tempo em dias
- -mtime → modificação
- -ctime → metadata
- -atime → acesso

### Tempo em minutos
- -mmin → modificação
- -cmin → metadata
- -amin → acesso

### Boas práticas para programadores
- Sempre testar primeiro sem -delete
- Usar -type f para evitar apagar diretórios por engano
- Combinar com -mtime para limpeza automática (logs, builds, etc.)
