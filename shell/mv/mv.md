# mv

## O que é
mv (move) é um comando usado para mover ou renomear files e directories no Linux/Ubuntu.

## Para que serve
Serve para reorganizar arquivos, mover projetos para diretórios diferentes, renomear arquivos ou diretórios, e fazer mudanças rápidas na estrutura de um projeto. Ao contrário do cp, mv remove o original ao mover.

## Como usar
mv [opções] source destination

## Exemplos

### Mover um arquivo para outro diretório
mv file.txt target_folder/

### Mover múltiplos arquivos para um diretório
mv file1.txt file2.txt target_folder/

### Renomear um arquivo
mv old_name.txt new_name.txt

### Renomear um diretório
mv old_folder/ new_folder/

### Mover com confirmação antes de sobrescrever
mv -i file.txt target_folder/

### Forçar mover sem avisos
mv -f file.txt target_folder/

### Mostrar detalhes do movimento
mv -v file.txt target_folder/

## Flags úteis

### Pede confirmação antes de sobrescrever files
-i

### Força mover, sobrescrevendo sem aviso
-f

### Move apenas se o source for mais recente ou destino não existir
-u

### Mostra detalhes da operação (verbose)
-v

### Combinações comuns
-> mv -iv file.txt target_folder/ → pergunta antes de sobrescrever e mostra detalhes
-> mv -u old_project/ backup_project/ → move apenas se necessário para atualizar backups

## Notas

- mv remove o arquivo original ao mover.
- Para mover arquivos entre sistemas de arquivos diferentes, mv copia e depois apaga o original automaticamente.
- Renomear é apenas um movimento dentro do mesmo diretório ou filesystem.
- Use -i ou -u para evitar sobrescrever arquivos importantes acidentalmente.

## Conceitos importantes

### Diferença entre mv e cp
- cp → copia arquivos mantendo o original
- mv → move arquivos ou diretórios, removendo o original

### Sobrescrever arquivos
- Sem flags, mv sobrescreve automaticamente arquivos existentes no destino.
- Com -i, pede confirmação antes de sobrescrever.
- Com -u, move apenas se o arquivo de origem for mais novo ou não existir no destino.

### Verbose (-v)
- Mostra os arquivos/diretórios à medida que são movidos, útil para grandes operações.

### Renomear vs Mover
- Renomear é apenas mudar o nome do arquivo/diretório dentro do mesmo filesystem.
- Mover pode envolver mudança de filesystem, copiando e apagando o original.
