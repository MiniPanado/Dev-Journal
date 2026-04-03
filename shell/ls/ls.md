# ls

## O que é
Lista o conteúdo de diretórios no terminal.

## Para que serve
É útil para ver rapidamente quais ficheiros e pastas existem num diretório e obter informações sobre eles.

## Como usar
ls [opções][diretório]

## Exemplos

### Listar ficheiros no diretório atual
ls

### Listar ficheiros de outro diretório
ls /caminho/do/diretório

### Listar ficheiros incluindo ficheiros ocultos
ls -a

### Listar ficheiros incluindo ficheiros ocultos (exceto . e ..)
ls -A

### Listar ficheiros em formato longo (mais informações)
ls -l

### Combinar: ocultos + detalhado
ls -la

### Listar ficheiros com tamanho humano legível
ls -lh
#### Ex: 1K,2M,3G

### Ordenar por data de modificação (mais recente primeiro)
ls -lt

### Ordenar por tamanho (maior primeiro)
ls -lS

### Ordenar por extensão
ls -X

### Ordem sem ordenação (original)
ls -U

### Ordem inversa
ls -lr

### Mostrar diretórios apenas
ls -d */

### Listar recursivamente subdiretórios
ls -R

### Mostrar lista em colunas
ls -C

### Listar com cores e ícones (dependente do terminal)
ls --color=auto

## Flags úteis

### Mostrar ficheiros ocultos (começam com .)
-a

### Mostrar ficheiros ocultos (exceto . e ..)
-A

### Mostrar detalhes: permissões, proprietário, grupo, tamanho e data
-l

### Torna os tamanhos legíveis (human readable)
-h

### Um ficheiro por linha
-1

### Lista separada por vírgulas
-m

### Mostrar caracteres não imprimíveis como sequências de escape \xxx
-b

### Lista em colunas (padrão para saída em terminal)
-C

### Ordena por data de modificação (mais recente primeiro)
-t

### Ordena por tamanho (maior primeiro)
-S

### Ordena por extensão (ordem alfabética)
-X

### Não ordena (ordem original do sistema de ficheiros)
-U

### Inverte a ordem da listagem
-r

### Lista recursivamente todos os subdiretórios
-R

### Mostrar apenas os diretórios, não o conteúdo deles
-d

### Mostrar o inode de cada ficheiro
-i

### Mostrar tamanho em blocos
-s

### Mostrar User ID e Group ID em vez de nomes
-n

### Igual ao -l, mas sem grupo
-o

### Igual -l, mas sem proprietário
-g

### Adiciona símbolo ao tipo:
-F
#### / diretório
#### * executável
#### @ link simbólico

### Adiciona / aos diretórios
-p

### Coloriza a saída conforme tipo de ficheiro (pasta, executável, link...)
--color=auto

## Notas

- ls sozinho mostrar apenas ficheiros não ocultos, em ordem alfabética.
- Para grandes diretórios, combinar ls -lh ajuda a ler melhor os tamanhos.
- Pode combinar múltiplas flags: ls -lah lista tudo, em formato longo e legível.

## Conceitos importantes

### ls -l mostra:
-> permisões
-> número de links
-> proprietário
-> grupo
-> tamanho
-> data
-> nome

### Permissões
Representadas como rwx (read, write, execute) na coluna do ls -l

### Inode
Identificador interno único de um ficheiro no sistema

### Tamanho de ficheiro
Mostrado em bytes, mas com -h torna legível (K, M, G).

### Data de modificação
Mostra quando o ficheiro ou pasta foi alterado pela última vez.
