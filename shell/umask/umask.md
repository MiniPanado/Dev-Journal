# umask

## O que é
umask (user file creation mask) é um comando usado para definir as permissões padrão de novos arquivos e diretórios criados no sistema.

## Para que serve
Serve para controlar automaticamente as permissões iniciais de arquivos e diretórios, garantindo segurança e evitando permissões excessivas sem precisar usar chmod manualmente.

## Como usar
umask [valor]

## Exemplos

### Ver o valor atual da umask
umask

### Ver a umask em formato simbólico
umask -S

### Definir uma nova umask
umask 022

### Definir permissões mais restritas
umask 077

### Aplicar umask temporariamente (apenas na sessão atual)
umask 027

### Criar arquivo com umask aplicada
umask 022
touch arquivo.txt

### Criar diretório com umask aplicada
umask 022
mkdir pasta/

## Flags úteis

### Mostra a umask em formato simbólico (u=, g=, o=).
-S

### Combinações comuns
- umask 022 → arquivos: 644 | diretórios: 755
- umask 027 → arquivos: 640 | diretórios: 750
- umask 077 → arquivos: 600 | diretórios: 700

## Notas

- umask não define permissões diretamente → remove permissões do padrão.
- Afeta apenas arquivos/diretórios criados após a definição.
- A configuração é temporária (sessão atual), a menos que seja definida em arquivos como .bashrc ou .profile.

### Valores comuns:
- 022 → permissões padrão seguras para sistemas multiusuário
- 077 → permissões restritas (uso pessoal)

## Conceitos importantes

### Permissões padrão
#### Antes da umask ser aplicada:
- Arquivos → 666 (rw-rw-rw-)
- Diretórios → 777 (rwxrwxrwx)

### Como a umask funciona
A umask subtrai permissões do valor padrão.

- Exemplo: umask 022
    - Arquivos: 666 - 022 = 644 → rw-r--r--
    - Diretórios: 777 - 022 = 755 → rwxr-xr-x

### Explicação dos números
- 0 → nenhuma permissão removida
- 2 → remove escrita (w)
- 7 → remove tudo (rwx)

### Boas práticas para programadores
- Usar 022 como padrão em ambientes normais.
- Usar 077 para dados sensíveis ou ambientes privados.
- Definir umask no .bashrc para persistência.
- Entender que a umask remove permissões, não adiciona.
- Verificar permissões finais com ls -l.
