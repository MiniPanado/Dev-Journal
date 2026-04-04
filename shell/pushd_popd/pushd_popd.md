# pushd + popd

## O que é
pushd muda para outro diretório e adiciona o diretório atual à stack de diretórios.
popd retorna ao diretório anterior, removendo-o da stack.

## Para que serve
Permite navegar rapidamente entre múltiplos diretórios sem perder o local original.
Muito útil em scripts ou quando precisas alternar entre vários diretórios temporariamente.

## Como usar
pushd [diretório]
popd

## Exemplos

### Ir para outro diretório e adicionar o atual à stack
pushd /home/utilizador/Projetos

### Voltar ao diretório anterior (removendo da stack)
popd

### Ver a stack de diretórios
dirs -v

## Flags úteis

### Troca o diretório atual com o N-ésimo diretório da stack
pushd +N

### Troca o diretório atual com o N-ésimo diretório da stack, mas contado de trás para frente
pushd -N

### Remove o N-ésimo diretório da stack, sem alterar o diretório atual
popd +N

### Remove o N-ésimo diretório da stack, mas contando de trás para frente
popd -N

## Notas

- pushd combina cd + stack de diretórios - cada vez que usas pushd, o diretório atual é guardado.
- popd retorna ao último diretório guardado, útil para scripts que precisam voltar ao ponto inicial.
- dires é útil para visualizar a stack a qualquer momento.
- Pode-se combinar com pwd para verificar exatamente em qual diretório estás.

## Conceitos importantes

### Stack de diretórios
É uma estrutura tipo "último a entra, primeiro a sair" (LIFO).
pushd adiciona ao topo, popd remove do topo.
#### Exemplo de fluxo
-> Começas em ~/Documents
-> pushd ~/Projects → vais para ~/Projects e ~/Documents fica na stack.
-> pushd ~/Downloads → vais para ~/Downloads, stack: ~/Downloads ~/Projects ~/Documents
-> popd → volta para ~/Projects, stack: ~/Projects ~/Documents
