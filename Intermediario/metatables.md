## 4.1 Metatables

Começando a entrar mais nas individualidades de Lua chegamos no assunto de Metatables, poderiamos chamar de "meta tabelas" mas por questões estéticas prefiro manter "metatables". Esse conceito é um dos mais poderosos dentro de lua, flexibilizando bastante a sintaxe da linguagem.

Metatables são tabelas que ajudam a controlar o comportamento de outras tabelas. Conseguimos desde alterar o comportamento de certos operadores até adicionar valores padrões para indices novos e muito mais.

### Lista de meta métodos

| Índice     | Comportamento                                                |
|------------|--------------------------------------------------------------|
| __add      | Executa sempre que o operador de soma "+" é chamado          |
| __sub      | Executa sempre que o operador de subtração "-" é chamado     |
| __mul      | Executa sempre que o operador de multiplicação "*" é chamado |
| __div      | Executa sempre que o operador de divisão "/" é chamado       |
| __mod      | Executa sempre que o operador de módulo "%" é chamado        |
| __unm      | Executa sempre que o operador de unário "-" é chamado        |
| __concat   | Executa sempre que o operador de concatenação ".." é chamado |
| __eq       | Executa sempre que o operador de comparação "==" é chamado   |
| __it       | Executa sempre que o operador de comparação "<" é chamado    |
| __le       | Executa sempre que o operador de comparação "<=" é chamado   |
| __call     | Executa sempre que a tabela é chamada como função "table()"  |
| __tostring | Executa sempre que é chamado a função tostring() é chamada   |
| __len      | Executa sempre que o operador "#" é chamado                  |
| __newindex | Executa sempre que um novo indice é acessado                 |
| _index     | Executa sempre que um indice declarado é acessado            |

Próximo: 
- [Variáveis](/Intermediario/OOP.md)