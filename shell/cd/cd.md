# cd

## O que é
cd (change directory) é um comando usado para navegar entre diretórios no sistema de arquivos do Linux/Ubuntu.

## Para que serve
Serve para mudar de diretório no terminal, permitindo acessar diferentes partes do sistema, projetos e arquivos.

## Como usar
cd [opção] [caminho]

## Exemplos

### Ir para um diretório
cd projects

### Voltar um nível (diretório pai)
cd ..

### Ir para o diretório home
cd | cd ~

### Ir para um caminho absoluto
cd /home/user/projects
#### Navega diretamente para o caminho completo.

### Ir para um caminho relativo
cd projects/javascript
#### Navega a partir do diretório atual.

### Voltar para o diretório anterior
cd -
#### Alterna entre o diretório atual e o último diretório visitado.

### Ir para uma pasta com espaços no nome
cd "my folder" | cd my\ folder

## Flags úteis

- O cd praticamente não usa flags no dia a dia.
- Ele é simples e baseado em caminhos.

## Notas

- cd funciona com caminhos absolutos e relativos.
- Use cd - para alternar rapidamente entre dois diretórios (muito útil).
- Use ~ como atalho para o home.
- Se o caminho não existir, o comando falha.

## Conceitos importantes

### Caminho absoluto
Caminho completo desde a raiz /.

### Caminho relativo
Caminho baseado no diretório atual.

### Diretório pai (..)
Representa o diretório acima do atual.

### Diretório atual (.)
Representa o diretório atual (usado mais em outros comandos como find).

### Home (~)
Atalho para o diretório do usuário.

### Diretório anterior (-)
Permite alternar rapidamente entre dois diretórios.

### Boas práticas para programadores
- Usa cd - para alternar entre pastas (muito útil em projetos).
- Prefere caminhos relativos dentro de projetos (mais rápido).
- Usa autocomplete (TAB) para evitar erros de digitação.
