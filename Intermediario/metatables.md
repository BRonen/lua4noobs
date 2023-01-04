## 4.1 Metatables

Começando a entrar mais nas individualidades de Lua chegamos no assunto de Metatables, poderiamos chamar de "meta tabelas" mas por questões estéticas prefiro manter "metatables". Esse conceito é um dos mais poderosos dentro de lua, flexibilizando bastante a sintaxe da linguagem.

Metatables são tabelas que ajudam a controlar o comportamento de outras tabelas. Conseguimos desde alterar o comportamento de certos operadores até adicionar valores padrões para indices novos e muito mais.

## Lista de meta métodos

| Índice                   | Comportamento                                                |
|--------------------------|--------------------------------------------------------------|
| [__add](aritmetica)      | Executa sempre que o operador de soma "+" é chamado          |
| [__sub](aritmetica)      | Executa sempre que o operador de subtração "-" é chamado     |
| [__mul](aritmetica)      | Executa sempre que o operador de multiplicação "*" é chamado |
| [__div](aritmetica)      | Executa sempre que o operador de divisão "/" é chamado      |
| [__mod](aritmetica)      | Executa sempre que o operador de módulo "%" é chamado        |
| [__unm](unario)          | Executa sempre que o operador unário "-" é chamado        |
| [__concat](concatenação) | Executa sempre que o operador de concatenação ".." é chamado |
| [__eq](comparação)       | Executa sempre que o operador de comparação "==" é chamado   |
| [__it](comparação)       | Executa sempre que o operador de comparação "<" é chamado    |
| [__le](comparação)       | Executa sempre que o operador de comparação "<=" é chamado   |
| [__call](call)           | Executa sempre que a tabela é chamada como função "table()"  |
| [__tostring](conversao)  | Executa sempre que é chamado a função tostring() é chamada   |
| [__len](tamanho)         | Executa sempre que o operador "#" é chamado                  |
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

Próximo: 
- [Variáveis](/Intermediario/OOP.md)