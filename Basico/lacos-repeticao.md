## 3.4 Laços de repetição

Um dos recursos comuns mais interessantes de se usar também são os laços de repetição, em Lua temos dois tipos de laços: o ```while```, o ```for``` e o ```repeat until```. Laços de repetição tentam se basear na idéia de loops, servem pra repetir um certo trecho de código.

#### While do
Esse laço serve basicamente para repetir um trecho de código **enquanto** uma condição for verdadeira.
```lua
while condição do
    ...
end
```

O significado desse código é "**enquanto** essa **condição** for verdadeira, **execute** esse trecho de código até chegar no **fim**". Por exemplo:
```lua
numero = 5
while numero >= 1 do
    print(numero)
    numero = numero - 1
end
```
Resultado:
```
5
4
3
2
1
```

#### Repeat until
Podemos resumir o ```repeat until``` como um ```while``` com algumas coisas um pouco trocadas.
```lua
repeat
    ...
until condição
```

Isso seria equivalente a "**repita** esse trecho de código **até** essa condição ser verdadeira". Por exemplo:
```lua
numero = 5
repeat
    print(numero)
    numero = numero - 1
until numero < 1
```
Resultado:
```
5
4
3
2
1
```

#### For do
O comando ```for``` é tratado um pouco diferente por ser dividido entre a versão numérica e a genérica. Mas ambos usam o mesmo conceito, significa "para cada valor dentro desses valores, use o valor para executar esse pedaço de código até o final".

##### Versão numérica
A versão numérica é bem simples, ele executa o loop para cada valor entre dois números (inicial e final). Para acessar esse valor, o laço salva esse valor em uma variavel cujo nome você escolhe.
```lua
for variavel = inicial, final do
    ...
end
```

Exemplo básico:

```lua
for numero = 1, 5 do
    print(numero)
end
```
Resultado:
```
1
2
3
4
5
```

Um detalhe muito útil na versão numérica é também ser capaz de controlar o salto entre os valores escolhidos, o valor padrão é 1 pois ele puxa um valor pra cada número.
```lua
for variavel = inicial, final, salto do
    ...
end
```
Um exemplo pulando um valor a cada número dentro dos parâmetros passados:
```lua
for numero = 1, 10, 2 do
    print(numero)
end
```
Resultado:
```
1
3
5
7
9
```

Esse valor de salto também pode ser usado com valores negativos. Por exemplo:
```lua
for numero = 5, 1, -1 do
    print(numero)
end
```
Resultado:
```
5
4
3
2
1
```

##### Versão genérica
Essa versão serve pra percorrer os valores de uma tabela através de um [iterador](https://www.lua.org/pil/7.1.html). O conteúdo dela será explorado melhor na [página de tabelas](/Basico/tabelas.md).

#### Break
O ```break``` serve para impedir um loop de rodar outra vez o mesmo trecho de código mesmo que não tenha alcançado as condições propostas. Alguns exemplos:
```lua
print('while + break:')
numero = 10
while numero >= 1 do
    if numero == 4 then
        break
    end
    print(numero)
    numero = numero - 1
end

print('repeat until + break:')
numero = 10
repeat
    if numero == 4 then
        break
    end
    print(numero)
    numero = numero - 1
until numero < 1

print('for + break:')
for numero = 3, 10 do
    if numero == 8 then
        break
    end
    print(numero)
end
```
Resultado:
```
while + break:
10
9
8
7
6
5
repeat until + break:
10
9
8
7
6
5
for + break:
3
4
5
6
7
```

Próximo:
- [Funções](/Basico/funcoes.md)