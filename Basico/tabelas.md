## 3.2 Tabelas

Em Lua o tipo mais interessante é conhecido como [Tabela](http://lua-users.org/wiki/TablesTutorial), a idéia principal em volta dessa estrutura é servir de "container" pra outros tipos de dados. Podendo ser usada ao equivalente de um [Array](https://pt.wikipedia.org/wiki/Arranjo_(computação)), um Dicionário ou um [Objeto]().

```lua
--arrays em lua começam com índice 1
local arr = {"a", "b", "c"}
print(arr[3] .. arr[2] .. arr[1])
```
```
cba
```

## Arrays

Usar tabelas como arrays é incrivelmente simples, separei em uma página própria pra organizar melhor:

> [Arrays](/Basico/tabelas/arrays.md)


## Dicionário

Tabelas também podem ser usadas pra salvar valores em índices que não são apenas números, basicamente qualquer tipo de dado pode ser usado como indíce menos o Nil.

```lua
> dict = {}

> dict[-1]     = '-1' --negative number
> dict[1.0]    = '1.0' --float number
> dict['one']  = 'one' --string
> dict[true]   = 'true' --boolean

> function test() end
> dict[test] = 'test' --function

> anotherTable = {}
> dict[anotherTable] = 'another table' --table

> dict[-1] --negative number
'-1'
> dict[1.0] --float number
'1.0'
> dict['one'] --string
'one'
> dict[true] --boolean
'true'
> dict[test] --function
'test'
> dict[anotherTable] --table
'another table'
```
