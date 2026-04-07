# chown

## O que é
chown (change owner) é um comando usado para alterar o dono e/ou o grupo de arquivos e diretórios no sistema de arquivos.

## Para que serve
Serve para gerenciar a propriedade de arquivos e diretórios, permitindo controlar quem tem permissões e responsabilidades sobre determinados recursos, essencial em sistemas multiusuário e em administração de servidores.

## Como usar
chown [opções] [novo_dono][:novo_grupo] [arquivo/diretório]

## Exemplos

### Alterar apenas o dono do arquivo
chown joao arquivo.txt

### Alterar dono e grupo
chown joao:desenvolvedores arquivo.txt

### Alterar apenas o grupo
chown :desenvolvedores arquivo.txt

### Aplicar recursivamente em um diretório
chown -R joao:pessoal pasta/

### Usar UID ou GID ao invés de nomes
chown 1001:1001 arquivo.txt

### Alterar múltiplos arquivos de uma vez
chown joao arquivo1.txt arquivo2.txt arquivo3.txt

## Flags úteis

### Aplica alterações recursivamente em diretórios e seus conteúdos.
-R

### Altera apenas se o arquivo tiver o dono e grupo especificado.
--from=OLD_OWNER:OLD_GROUP

### Copia dono e grupo de outro arquivo.
--reference=arquivo_referencia

### Mostra detalhes das alterações feitas (verbose).
-v

### Mostra apenas arquivos que foram realmente modificados.
-c

### Combinações comuns
- chown joao arquivo.txt → muda dono
- chown joao:desenvolvedores arquivo.txt → muda dono e grupo
- chown -R joao:pessoal pasta/ → muda tudo dentro da pasta recursivamente
- chown --reference=outro.txt arquivo.txt → igualar dono/grupo a outro arquivo

## Notas

- Apenas o root ou o dono do arquivo (dependendo do sistema) pode alterar o dono.
- Alterar dono de diretórios importantes pode afetar permissões e funcionamento de serviços.
- É comum combinar com chmod para ajustar permissões depois de mudar dono/grupo.
- UID e GID podem ser usados em vez de nomes de usuário ou grupo.

## Conceitos importantes

### Dono (owner)
- O usuário principal que possui o arquivo/diretório.

### Grupo
- Conjunto de usuários que compartilham permissões.

### Formato de arquivos

#### Exemplo: ls -l -> -rw-r--r-- 1 joao pessoal 1024 Apr 6 12:30 arquivo.txt
- joao → dono do arquivo
- pessoal → grupo do arquivo

### Recursividade (-R)
- Altera dono/grupo de todas as pastas e arquivos internos.

### UID/GID
- UID → identificador numérico do usuário
- GID → identificador numérico do grupo

### Boas práticas para programadores
- Evitar mudar dono de arquivos do sistema ou de outros usuários sem cuidado.
- Usar -R apenas em diretórios controlados para não quebrar permissões críticas.
- Verificar alterações com ls -l antes e depois de executar chown.
- Combinar com chmod quando necessário para ajustar permissões junto com dono/grupo.
- Em scripts, preferir nomes de usuário/grupo em vez de números UID/GID para clareza.
