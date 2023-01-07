## [4.1 Metatables](https://www.lua.org/manual/5.1/manual.html#2.8)

Começando a entrar mais nas individualidades de Lua chegamos no assunto de Metatables, poderiamos chamar de "meta tabelas" mas por questões estéticas prefiro manter "metatables". Esse conceito é um dos mais poderosos dentro de lua, flexibilizando bastante a sintaxe da linguagem.

Metatables são tabelas que ajudam a controlar o comportamento de outras tabelas. Conseguimos desde alterar o comportamento de certos operadores até adicionar valores padrões para indices novos e muito mais.

## Lista de meta métodos


<small>

[Documentação completa](https://www.lua.org/manual/5.1/manual.html#2.8)

</small>


| Índice                   | Comportamento                                                |
|--------------------------|--------------------------------------------------------------|
| [__add](aritmetica)      | Executa sempre que o operador de soma "+" é chamado          |
| [__sub](aritmetica)      | Executa sempre que o operador de subtração "-" é chamado     |
| [__mul](aritmetica)      | Executa sempre que o operador de multiplicação "*" é chamado |
| [__div](aritmetica)      | Executa sempre que o operador de divisão "/" é chamado       |
| [__mod](aritmetica)      | Executa sempre que o operador de módulo "%" é chamado        |
| [__pow](aritmetica)      | Executa sempre que o operador de módulo "^" é chamado        |
| [__unm](unario)          | Executa sempre que o operador unário "-" é chamado           |
| [__concat](concatenação) | Executa sempre que o operador de concatenação ".." é chamado |
| [__len](length)          | Executa sempre que o operador de length "#" é chamado        |
| [__eq](comparação)       | Executa sempre que o operador de comparação "==" é chamado   |
| [__it](comparação)       | Executa sempre que o operador de comparação "<" é chamado    |
| [__le](comparação)       | Executa sempre que o operador de comparação "<=" é chamado   |
| [__call](call)           | Executa sempre que a tabela é chamada como função "table()"  |
| [__tostring](conversao)  | Executa sempre que é chamado a função tostring() é chamada   |
| [__newindex](novo)       | Executa sempre que um novo indice é acessado                 |
| [_index](indice)         | Executa sempre que um indice declarado é acessado            |

<div id="aritmetica">
    
## Meta métodos aritméticos: __add, __sub, __mul, __div e __mod.

</div>

Sempre que definimos esses métodos, eles são chamados quando executamos seus respectivos operadores. Por exemplo

```lua
local obj = { value = 2 }
setmetatable(obj, {
    __add = function(a, b)
        return a.value + b
    end
})
print(obj + 3)
```

Nesse código criamos uma tabela e definimos o comportamento que deve ter quando for somada a outro valor, e nesse caso somamos o valor com a propriedade "value" dessa tabela e retornamos o resultado da soma.

```
5
```

Esse comportamento pode ser replicado para qualquer operador aritmético da lista.


<div id="unario">
    
## Meta método unário: __unm.

</div>

Quando tornamos um valor negativo pondo um "-" antes desse valor, esse meta método é chamado para retornar algo do mesmo jeito que números retornam seu próprio valor com sinal invertido.

```lua
local obj = { value = 2 }
setmetatable(obj, {
    __unm = function(a, b)
        return a.value * -2
    end
})
print(-obj)
```

Nesse código criamos uma tabela com um comportamento para que quando executamos o operador unário "-", seja retornado seu valor multiplicado por -2.

```
-4
```


<div id="concatenação">
    
## Meta método concatenação: __concat.

</div>

Quando usamos o operador ".." geralmente estamos tentando unir duas strings em uma só. Mas sempre que isso é feito com uma tabela, esse meta método é chamado para controlar o comportamento que essa tabela deve ter.

```lua
local obj = { value = "Lorem" }
setmetatable(obj, {
    __concat = function(a, b)
        return string.reverse(a.value .. " " .. b)
    end
})
print(obj .. "Ipsum")
```

Nesse código criamos uma tabela com um comportamento para que quando executamos o operador de concatenação "..", seja retornado seu valor concatenado e invertido.

```
muspI meroL
```

Próximo: 
- [Variáveis](/Intermediario/OOP.md)