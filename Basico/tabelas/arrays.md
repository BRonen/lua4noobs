### Arrays

O conceito de arrays é basicamente uma lista de elementos, em Lua implementamos essa estrutura usando tabela como base. A capacidade de acessar um índice númerico permite que acessemos a tabela de forma organizada.

```lua
--acessando cada posição do array e vendo seu valor
local array = {10, 20, 30}
for index = 1, 3 do
  print(array[index])
end
```

Um pequeno problema que surge é caso não tenhamos na mão o tamanho do array, pois não teremos controle sobre até onde acessar esse array. Para burlar isso podemos fazer algo como:

```lua
local array = {10, 20, 30}
local index = 1
while true do
  print(array[index])
  index = index + 1
  --caso o índice devolva o valor nulo, quebra o loop
  if not array[index] then break end
end
```

### Operador \#

Um operador muito útil quando queremos saber a quantidade de itens dentro de um array, podemos usar o operador *#*:

```lua
local array = {10, 20, 30}
print(#array)
```

Para simplificar o acesso de arrays, podemos reescrever o primeiro exemplo de arrays usando esse operador

```lua
...
--assim acessamos cada índice do primeiro ao último
for index = 1, #array do
  print(array[index])
end
```

### Iteradores

Um iterador é uma função que a cada chamada retorna um elemento do array, para facilitar é útil usar uma função construtora para controlar o escopo do tamanho do array e do índice atual da busca:

```lua
function list_iterator(array)
  local index = 0
  local n = table.getn(array)
  return function()
    index = index + 1
    if index <= n then return array[index] end
  end
end
```

Tendo feito um construtor para nosso iterador, podemos criar essa função e iterar sobre cada elemento de um array:

```lua
local array = {10, 20, 30}
iterator = list_iterator(array)
while true do
  local element = iterator()
  if element == nil then break end
  print(element)
end
```

Simplificando a iteração sobre cada elemento, é possível substituir o while com um ```For in```:

```lua
local array = {10, 20, 30}
for element in list_iterator(array) do
  print(element)
end
```

### Ipairs

Mas óbvio que é desnecessario sempre ficar criando iteradores como esse pelo seu código, como solução nativa a esse problema temos o ```ipairs()```:

```lua
local array = {10, 20, 30}
for index, element in ipairs(array) do
  print(element)
end
```