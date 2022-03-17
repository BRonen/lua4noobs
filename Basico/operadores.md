## 3.2 Operadores

### Operadores aritméticos

Em Lua é possível realizar operações matemáticas entre números através de simples operadores:

| Nome                 | Símbolo | Descrição                    |
| :------------------: | ------- | ---------------------------- |
| Soma                 | +       | Soma dois valores            |
| Subtração            | -       | Subtrai dois valores         |
| Multiplicação        | *       | Multiplica dois valores      |
| Divisão              | /       | Divide dois valores          |
| Módulo               | %       | Resto de divisão dos valores |
| Potenciação          | ^       | Eleva um valor pelo outro    |

Exemplo de operações feitas em Lua

```lua
> print(1 + 1)
2
> print(2 - 1)
1
> print(3 * 3)
9
> print(10 / 5)
2
> print(13 % 5)
3
> print(2 ^ 3)
8
```

E esses exemplos tambem se aplicam no uso de variáveis

```lua
> numero =  1
> print(numero)
1
> numero = numero * 2
2
> print(numero ^ 3)
8
```

### Operadores relacionais

Operadores relacionais servem basicamente pra testar uma certa condição e dizer se é verdadeira ou falsa. Isso torna esses operadores muito ligados ao tipo [boolean](/Basico/tipos/boolean-nil.md).

| Nome        | Símbolo | Descrição                                     |
| :---------: | ------- | --------------------------------------------- |
| Igual       | ==      | Compara se dois valores são iguais            |
| Diferente   | ~=      | Verifica se dois valores são diferentes       |
| Maior       | >       | Verifica se um valor é maior que outro        |
| Menor       | <       | Verifica se um valor é menor que outro        |
| Maior igual | >=      | Verifica se um valor é maior ou igual a outro |
| Maior igual | <=      | Verifica se um valor é menor ou igual a outro |

Os exemplos mais comuns desses operadores é usando números pela simplicidade no entendimento

```lua
> print(1 == 1)
true
> print(1 == 3)
false
> print(1 ~= 1)
false
> print(2 > 1)
true
> print(1 <= 0)
false
> print(1 >= 1)
true
...
```

Próximo: 
- [Estruturas condicionais](/Basico/condicionais.md)