# rm

## O que é
rm (remove) é um comando usado para apagar arquivos e diretórios no Linux/Ubuntu.

## Para que serve
Apaga arquivos e pastas que não precisam mais, limpa temporários e mantém o projeto organizado. (Permanente)

## Como usar
rm [opções] file1 file2 ...

## Exemplos

### Remover um arquivo simples
rm file.txt

### Remover múltiplos arquivos
rm file1.txt file2.txt file3.txt

### Remover arquivos com confirmação
rm -i file.txt
#### Pergunta antes de apagar cada arquivo.

### Remover todos os arquivos de um tipo
rm *.log

### Remover diretório e todo o seu conteúdo
rm -r directory

### Forçar remoção sem avisos
rm -f file.txt
#### Remove o arquivo mesmo que esteja protegido contra gravação, sem pedir confirmação.

## Flags úteis

### Remove diretórios e seus conteúdos recursivamente
-r | --recursive

### Força a remoção sem avisos
-f | --force

### Pede confirmação antes de apagar cada arquivo
-i

### Pede confirmação apenas se for apagar mais de 3 arquivos ou recursivamente
-I

### Evita atravessar sistemas de arquivos diferentes ao remover diretórios
--one-file-system
### Mostra arquivos à medida que são apagados (verbose)
-v

### Permite apagar a raiz / (muito perigoso)
--no-preserve-root

### Combinações comuns
-> rm -rf directory → remover diretório com tudo dentro, sem perguntas
-> rm -iv *.tmp → perguntar antes de apagar cada arquivo temporário
-> rm -rfv build/ → remover diretório recursivamente mostrando o progresso

## Notas

- Cuidado extremo: rm -rf pode apagar tudo sem aviso. Um erro de digitação pode destruir projetos ou até o sistema.
- Não existe "lixeira" por padrão; o arquivo é apagado imediatamente.
- Para segurança extra, use -i ou alias como alias rm='rm -i'.
- Pode ser combinado com curingas (*, ?) para remover padrões de arquivos.
- Nunca use sudo rm -rf / a menos que saiba exatamente o que está fazendo.

## Conceitos importantes

### Recursividade (-r)
Permite remover diretórios e tudo dentro deles, inclusive subdiretórios.

### Forçar (-f)
Ignora erros e permissões de arquivos, não pedindo confirmação.

### Confirmação interativa (-i)
Pergunta antes de remover cada arquivo; muito útil para evitar acidentes.

### Curingas
-> * → qualquer sequência de caracteres
-> ? → um único caractere
- Exemplo: rm *.log apaga todos arquivos .log

### Boas práticas para programadores
- Prefira rm -i para arquivos importantes do projeto.
- Use rm -rf somente em diretórios temporários ou quando tiver certeza absoluta.
- Considere usar versões seguras, como mover arquivos para uma pasta de "quarentena" antes de apagar permanentemente.
