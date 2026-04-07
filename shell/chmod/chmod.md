# chmod

## O que é
chmod (change mode) é um comando usado para alterar as permissões de acesso de arquivos e diretórios no sistema de arquivos.

## Para que serve
Serve para controlar quem pode ler, escrever ou executar arquivos e diretórios, garantindo segurança e organização no sistema, especialmente em ambientes multiusuário e em desenvolvimento.

## Como usar
chmod [opções] [permissões] [arquivo/diretório]

## Exemplos

### Dar permissão de execução a um arquivo
chmod +x script.sh

### Remover permissão de escrita
chmod -w arquivo.txt

### Definir permissões usando modo numérico
chmod 755 script.sh

### Definir permissões específicas para usuário, grupo e outros
chmod u=rwx,g=rx,o=r arquivo.txt

### Aplicar permissões recursivamente
chmod -R 755 pasta/

### Remover todas as permissões de outros usuários
chmod o= arquivo.txt

### Adicionar permissão de leitura para grupo
chmod g+r arquivo.txt

### Definir SUID
chmod u+s programa

### Definir SGID
chmod g+s pasta/

### Definir Sticky Bit
chmod +t pasta/

## Flags úteis

### Aplica permissões recursivamente em diretórios e seus conteúdos.
-R

### Permissões

#### Permissões simbólicas
- u → usuário (owner)
- g → grupo
- o → outros
- a → todos

#### Operadores
- + → adiciona permissão
- - → remove permissão
- = → define exatamente as permissões

#### Tipos de permissão
- r → leitura (read)
- w → escrita (write)
- x → execução (execute)

#### Permissões especiais
- s → SUID / SGID
- t → Sticky Bit

#### Modo numérico (octal)
- 4 → leitura (r)
- 2 → escrita (w)
- 1 → execução (x)

### Combinações comuns
- chmod 755 arquivo → dono pode tudo, outros só leem/executam
- chmod 644 arquivo → dono escreve/le, outros só leem
- chmod +x script.sh → torna script executável
- chmod -R 755 pasta/ → aplica permissões a toda a pasta

## Notas

- Permissões são fundamentais para segurança no Linux.
- chmod não altera o dono do arquivo (isso é feito com chown).
- Usar -R com cuidado → pode alterar muitos arquivos de uma vez.
- Scripts precisam de permissão x para serem executados.
- Permissões especiais podem alterar o comportamento de execução e acesso.

## Conceitos importantes

### Estrutura de permissões

#### Exemplo: -rwxr-xr--
- 1º caractere → tipo (arquivo, diretório ou link)
- 3 seguintes → permissões do usuário (owner)
- 3 seguintes → permissões do grupo
- 3 últimos → permissões de outros

### Modo numérico explicado

#### Exemplo: 755
- 7 → 4+2+1 → rwx (usuário)
- 5 → 4+1 → r-x (grupo)
- 5 → 4+1 → r-x (outros)

### Diretórios vs arquivos

#### Em arquivos:
- r → ler conteúdo
- w → editar
- x → executar
#### Em diretórios:
- r → listar conteúdo
- w → criar/remover arquivos
- x → entrar no diretório

### Permissões especiais

#### SUID (Set User ID)
- Quando aplicado a um arquivo executável, o programa é executado com os privilégios do dono do arquivo.
- Exemplo clássico: /usr/bin/passwd
- Representação: s no lugar do x do usuário
- Exemplo: -rwsr-xr-x

#### SGID (Set Group ID)
- Em arquivos: executa com permissões do grupo
- Em diretórios: novos arquivos herdam o grupo do diretório
- Representação: s no lugar do x do grupo
- Exemplo: -rwxr-sr-x

#### Sticky Bit
- Usado em diretórios
- Apenas o dono do arquivo pode apagar/modificar, mesmo que outros tenham permissão de escrita
- Muito usado em /tmp
- Representação: t no lugar do x dos outros
- Exemplo: drwxrwxrwt

### Modo numérico com permissões especiais
- 4 → SUID
- 2 → SGID
- 1 → Sticky Bit

#### Exemplos:
- 4755 → SUID + 755
- 2755 → SGID + 755
- 1755 → Sticky Bit + 755

### Permissões padrão (umask)
- Define permissões padrão ao criar arquivos/diretórios.

### Boas práticas para programadores
- Evitar usar 777 (acesso total para todos) → risco de segurança.
- Dar +x apenas a arquivos que precisam ser executados.
- Usar 644 para arquivos comuns e 755 para scripts/diretórios.
- Verificar permissões com ls -l antes e depois de alterar.
- Ter cuidado com chmod -R em diretórios importantes.
- Usar SUID com extremo cuidado (pode criar vulnerabilidades).
- Usar SGID em diretórios compartilhados para manter consistência de grupo.
- Usar Sticky Bit em diretórios públicos (ex: /tmp).
