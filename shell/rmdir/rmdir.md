# rmdir

## O que é
rmdir (remove directory) é um comando usado para remover diretórios vazios no Linux/Ubuntu.

## Para que serve
Serve para apagar pastas que não contêm arquivos ou subpastas, ajudando a manter seu sistema de arquivos organizado.

## Como usar
rmdir [opções] nome_do_diretório

## Exemplos

### Remover um diretório vazio
rmdir projects

### Remover múltiplos diretórios vazios
rmdir pasta1 pasta2 pasta3

### Remover diretórios pais vazios
rmdir -p projects/python/src
#### Remove src, depois python, e depois projetos se cada um estiver vazio.

### Mensagem de confirmação ao remover
rmdir -v projetos
#### Mostra "rmdir: removed directory ‘projetos’" após apagar.

## Flags úteis

### Remove diretórios pais vazios em cascata
-p

### Mostra mensagens sobre os diretórios removidos
-v

## Notas

- rmdir só funciona com diretórios vazios.
- Para apagar diretórios com arquivos ou subpastas, use rm -r.
- É seguro usar quando quer limpar pastas antigas sem arriscar apagar arquivos por engano.

## Conceitos importantes

### Diretório vazio
Um diretório sem arquivos ou subdiretórios dentro dele.

### Flag -p
Permite remover toda a árvore de diretórios vazios de uma vez, do mais interno para o mais externo

### Diferença entre rmdir e rm -r
-> rmdir: apenas diretórios vazios
-> rm -r: remove diretórios mesmo com conteúdo
