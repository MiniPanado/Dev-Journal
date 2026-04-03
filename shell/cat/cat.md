# cat

## O que é
Exibe o conteúdo de ficheiros no terminal e permite concatená-los.

## Para que serve
É muito útil para visualizar rapidamente ficheiros pequenos ou juntar vários ficheiros num só.

## Como usar
cat ficheiro

## Exemplos

### Ver ficheiro
cat notas.txt

### Ver vários ficheiros
cat a.txt b.txt

### Juntar ficheiros
cat a.txt b.txt > tudo.txt

### Criar ficheiro
cat > novo.txt
#### escrever e depois CTRL + D

### Usar stdin com -
cat f.txt - g.txt
#### Saída: conteúdo de f.txt, depois o que você digitar, depois g.txt
#### Digite algo e depois CTRL + D para finalizar a entrada manual

## Flags úteis

### Numerar todas as linhas
cat -n ficheiro.txt

### Numerar apenas linhas não vazias
cat -b ficheiro.txt

### Mostrar new lines como $
cat -E ficheiro.txt

### Mostrar caracteres invisíveis
cat -v ficheiro.txt

### Mostrar caracteres invisíveis e new lines como $
cat -e ficheiro.txt | cat -vE ficheiro.txt

### Mostrar tabs como ^I
cat -T ficheiro.txt

### Mostrar caracteres invisíveis e tabs como ^I
cat -t ficheiro.txt | cat -vT ficheiro.txt

### Mostrar caracteres invisíveis, tabs como ^I e new lines como $
cat -A ficheiro.txt | cat -vET

### Combinar flags (ex.: numerar + mostrar new lines)
cat -n -E ficheiro.txt

### Remover múltiplas linhas em branco consecutivas (deixando apenas uma)
cat -s ficheiro.txt

## Notas

- Não usar em ficheiros muito grandes → usar less
- ">" substitui o conteúdo do ficheiro
- ">>" adiciona ao ficheiro

## Conceitos importantes

### New line (\n)
Carácter invisível que indica o fim de uma linha.

### $ no cat -E
Mostra onde está o new line (fim da linha).
Não faz parte do ficheiro.
