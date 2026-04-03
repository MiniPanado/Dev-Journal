# pwd

## O que é
Mostra o caminho completo do diretório atual no terminal

## Para que serve
É útil para saber exatamente onde estás no sitema de ficheiros, especialmente quando trabalhas com múltiplos diretórios ou scripts.

## Como usar
pwd [opções]

## Exemplos

### Mostrar diretório atual
pwd

### Usar com echo (em scripts)
echo "Estamos em $(pwd)"

### Guardar o caminho numa variável
diretorio_atual=$(pwd)

## Flags úteis

### mostra o caminho lógico, ou seja, preserva os links simbólicos e reflete o percurso que fizeste (incluindo atalhos).
-L
#### caminho "como navegaste"
##### Ex.: Se /home/utilizador/docs é link para /mnt/drive/docs, ele mostra /home/utilizador/docs.

### mostra o caminho físico/real, resolvendo todos os links simbólicos para o caminho verdadeiro no sistema de ficheiros.mostra o caminho físico/real, resolvendo todos os links simbólicos para o caminho verdadeiro no sistema de ficheiros.
-P
#### caminho "como realmente é no sistema"
##### Ex.: Se /home/utilizador/docs é link para /mnt/drive/docs, ele mostra /mnt/drive/docs.

## Notas

- pwd não altera nada, apenas mostra o caminho.
- Útil para scripts que precisam do diretório de trabalho atual.
- Quando usado dentro de scripts, combina bem com cd, ls e cp.
- Para links simbólicos, pwd -L mantém o caminho lógico (atalho), enquanto pwd -P mostra o caminho real (físico).

## Conceitos importantes

### Link simbólico (soft link)
- É um atalho para outro ficheiro ou diretório.
- Pode apontar para ficheiros em outros sistemas de ficheiros.
- Se o ficheiro original for apagado, o link simbólico fica quebrado.

### Hard link
- É um outro nome para o mesmo ficheiro.
- Não pode atravessar sistemas de ficheiros diferentes.
- Se o ficheiro original for apagado, o hard link continua funcionando, pois aponta diretamente para os dados no disco.

### Diretório atual
O diretório onde estás no momento.
-> cd altera o diretório atual.

### Caminho absoluto
Começa na raiz / e mostra a localização completa.
-> Ex: /home/utilizador/Documents

### Caminho relativo
Baseado no diretório atual.
-> Ex: ./projetos ou ../imagens

### Permissões e inode
- Links simbólicos e hard links mostram diferentes informações em ls -l e ls -i.
- Hard links compartilham inode, links simbólicos têm inode próprio e apontam para outro ficheiro.
