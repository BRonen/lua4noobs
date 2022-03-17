## 3.3 Estruturas condicionais

Agora que você tem uma noção de operadores relacionais, pode entender mais fácil como funcionam estruturas condicionais. Um dos conceitos mais usados dentro da programação é o ```if```, traduzindo seria algo como "se", é basicamente a idéia de uma escolha de acordo com uma condição.

Dentro de Lua, um If é escrito assim:
```lua
if condição then
    ...
end
```

O ```if``` define o começo da estrutura, depois vemos uma condição que pode ser verdadeira ou falsa e se for verdadeira então o trecho de código entre o ```then``` e o ```end``` é executado.

Claro que a primeira coisa que vem em mente quando pensamos em verdadeiro e falso são os booleans e já associando uma coisa com a outra, podemos montar códigos assim
```lua
if 1 == 1 then
    print('1 == 1 é verdadeiro')
end
if 1 ~= 2 then
    print('1 ~= 2 é verdadeiro')
end
if 2 == 3 then
    print('esse trecho nunca vai ser executado')
end
```

Chegando nesse ponto, e se eu quiser executar um trecho caso seja uma condição verdadeira mas queira rodar outra apenas se for falsa? Pra esse caso temos o ```else```
```lua
if condição then
    print('esse trecho executa se a condição for true')
else
    print('esse trecho executa se a condição for false')
end
```

Exemplo de como aplicar isso
```lua
if 1 > 0 then
    print('1 é maior que 0')
else
    print('1 não é maior que 0')
end
```

Um dos casos mais feios de código possível são os [códigos hadouken](https://diogommartins.wordpress.com/2016/08/22/como-se-defender-de-ifs-hadouken/) então para tentar evitar muito ```ìf``` e ```else``` em cascata, existem o ```elseif```
```lua
if condição then
    print('esse trecho executa se a condição for true')
elseif outra-condição then
    print('esse trecho executa se a condição for false')
end
```

Isso funciona muito bem quando tem mais de uma opção e o código a executar dependa disso como nesse exemplo
```lua
operador = '*'
numero = 10

if operador == '+' then
    print(numero + 2)

elseif operador == '-' then
    print(numero - 2)

elseif operador == '*' then
    print(numero * 2)

elseif operador == '/' then
    print(numero / 2)
end
```
E o resultado desse exemplo é "20"

Próximo:
- [Laços de repetição](/Basico/lacos-repeticao.md)