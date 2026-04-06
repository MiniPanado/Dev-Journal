# touch

## O que é
touch é um comando usado para criar arquivos vazios ou atualizar a data e hora de acesso e modificação de arquivos existentes no sistema de arquivos.

## Para que serve
Serve para criar rapidamente arquivos novos, preparar arquivos para edição, atualizar timestamps de arquivos ou diretórios sem alterar o conteúdo, e como ferramenta em scripts de automação.

## Como usar
touch [opções] [arquivo]

## Exemplos

### Criar um arquivo vazio
touch arquivo.txt

### Criar múltiplos arquivos vazios
touch arquivo1.txt arquivo2.txt arquivo3.txt

### Atualizar a data e hora de um arquivo existente
touch arquivo.txt

### Criar arquivo se não existir e atualizar timestamp se existir
touch arquivo.txt

### Especificar data e hora
touch -t 202604061230 arquivo.txt
#### Define data/hora para 6 de abril de 2026, 12:30

### Usar timestamp de outro arquivo
touch -r outro_arquivo.txt arquivo.txt
#### Faz arquivo.txt ter a mesma data/hora de outro_arquivo.txt

### Criar arquivos recursivamente em diretórios existentes
touch pasta1/arquivo.txt pasta2/arquivo2.txt

## Flags úteis

### Atualiza apenas o tempo de acesso.
-a

### Atualiza apenas o tempo de modificação.
-m

### Não cria arquivos novos, apenas atualiza os existentes.
-c | --no-create

### Define data e hora específicas.
-t [[CC]YY]MMDDhhmm[.ss]

### Usa a data/hora de outro arquivo como referência.
-r arquivo_referencia

### Define data/hora com formato legível (ex.: "6 Apr 2026 12:30").
-d "STRING_DE_DATA"

### Combinações comuns
- touch -a arquivo.txt → atualiza só acesso
- touch -m arquivo.txt → atualiza só modificação
- touch -c arquivo.txt → evita criar novo arquivo
- touch -t 202604061230 arquivo.txt → define data/hora exata

## Notas

- Por padrão, touch cria arquivos vazios se não existirem.
- Atualiza timestamps sem modificar o conteúdo.
- Útil para scripts que dependem de arquivos "novos" ou atualizados.
- Funciona em qualquer tipo de arquivo, inclusive links simbólicos (dependendo do sistema).

## Conceitos importantes

### Timestamps
- atime → última vez que o arquivo foi acessado
- mtime → última vez que o conteúdo foi modificado
- ctime → última vez que metadados foram alterados (não modificável diretamente pelo touch)

### Formatos de data
- -t → formato [[CC]YY]MMDDhhmm[.ss]
- -d → formato legível "6 Apr 2026 12:30" | "2026-04-06 18:58"

### Arquivos criados
- Se o arquivo não existe → touch cria arquivo vazio
- Se o arquivo existe → touch atualiza timestamps

### Boas práticas para programadores
- Testar flags -c para evitar criar arquivos indesejados.
- Usar touch em scripts de automação para atualizar dependências.
- Combinar com -t ou -d para simular arquivos modificados em testes.
- Evitar alterar timestamps de arquivos críticos sem necessidade.
