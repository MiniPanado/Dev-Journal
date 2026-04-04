# mkdir

## O que é
mkdir (make directory) é um comando usado para criar novos diretórios no sistema de arquivos do Linux/Ubuntu.

## Para que serve
É usado para organizar arquivos em pastas, criar estruturas de diretórios para projetos ou sistemas, e preparar locais para armazenar dados.

## Como usar
mkdir [opções] nome_do_diretório

## Exemplos

### Criar um diretório simples
mkdir projects

### Criar múltiplos diretórios de uma vez
mkdir photos songs documents

### Criar diretórios dentro de outros diretórios
mkdir projects/python
#### Se projects existir, cria a subpasta python dentro dela.

### Criar diretórios recursivamente
mkdir -p projects/python/src
#### Cria toda a árvore de diretórios, mesmo que projects/python ainda não exista.

### Criar diretório e mostrar mensagem
mkdir -v projects
#### Mostra "mkdir: created directory ‘projects’" após criar.

### Criar diretório com permissões específicas
mkdir -m 755 projects

## Flags úteis

### Cria diretórios pais que não existem
-p

### Mostra mensagens sobre os diretórios criados
-v

### Define permissões do diretório ao criar
-m [permissões]

## Notas

- Sem -p, mkdir falha se o diretório pai não existir.
- Permissões padrão dependem do umask do usuário.
- É uma boa prática usar -p para criar subpastas em projetos grandes.

## Conceitos importantes

### Diretório pai
Um diretório que contém outros diretórios ou arquivos.
#### Ex: projects é pai de projects/python.

### Permissões de diretórios
Controlam quem pode ler, escrever ou entrar no diretório.
#### Ex: 755 → dono pode ler/escrever/executar e os outros podem ler/executar.

### Flag -p
Permite criar toda a árvore de diretórios necessária em um único comando.
