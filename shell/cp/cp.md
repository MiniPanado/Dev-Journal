# cp

## O que é
cp (copy) é um comando usado para copiar arquivos e diretórios no Linux/Ubuntu.

## Para que serve
Serve para criar cópias de arquivos ou diretórios, fazer backups rápidos, duplicar projetos, ou mover arquivos de forma segura mantendo o original.

## Como usar
cp [opções] source destination

## Exemplos

### Copiar um arquivo simples
cp file.txt copy.txt

### Copiar múltiplos arquivos para um diretório
cp file1.txt file2.txt target_folder/

### Copiar diretório recursivamente
cp -r projects/ backup_projects/

### Copiar arquivo mantendo permissões e atributos
cp -p file.txt copy.txt
#### Mantém permissões, timestamps e owner do file.

### Copiar com confirmação antes de sobrescrever
cp -i file.txt copy.txt

### Copiar e sobrescrever automaticamente
cp -f file.txt copy.txtcp -f file.txt copy.txt

### Copiar com mensagens detalhadas
cp -v file.txt copy.txt

### Copiar apenas se o source for mais recente ou destino não existir
cp -u file.txt copy.txt
#### Útil para atualizar backups sem sobrescrever arquivos mais novos.

### Copiar evitando sobrescrever arquivos existentes
cp --update=none file.txt copy.txt
#### Não sobrescreve arquivos existentes no destino.

## Flags úteis

### Copia diretórios recursivamente
-r | -R

### Pede confirmação antes de sobrescrever arquivos
-i

### Força a cópia, sobrescrevendo arquivos sem aviso
-f

### Mostra detalhes do que está sendo copiado
-v

### Preserva permissões, owner e timestamps (metadados)
-p

### Preserva permissões, owner, timestamps e symbolic links (metadados)
-a

### Copia apenas se o source for mais recente ou destino não existir
-u

### Não sobrescreve arquivos existentes
--update=none

### Combinações comuns
-> cp -rv projects/ backup/ → copia recursivamente mostrando cada arquivo
-> cp -i file.txt copy.txt → evita sobrescrever acidentalmente
-> cp -pu file.txt copy.txt → preserva atributos e copia apenas se mais novo

## Notas

- cp não remove o arquivo original; é uma cópia.
- Para copiar muitos arquivos de forma segura, combine -i ou -u.
- Para copiar directories, sempre use -r ou -R.
- Para backups completos, cp -a (archive) é muito útil: preserva tudo (recursivo, permissões, symbolic links).

## Conceitos importantes

### Recursividade (-r)
Permite copiar diretórios e todo o seu conteúdo, incluíndo subdiretórios.

### Preservação (-p ou -a)
Mantém permissões, timestamps, owner e symbolic links (-a).

### Sobrescrever arquivos
-> Sem flags, cp sobrescreve automaticamente.
-> Com -i, pede confirmação antes de sobrescrever.
-> Com -u, copia apenas se o arquivo de origem for mais novo ou não existir.
-> Com --update=none, não sobrescreve arquivos existentes.

### Diferença entre cp e mv
- cp → copia, mantedo o original
- mv → move ou renomeia, remove o original
