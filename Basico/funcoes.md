## 3.5 Funções

As [funções](https://www.lua.org/pil/5.html) em Lua e na maioria das linguagens funcionam como um comando que executa um trecho de código.
Nada muito complexo, por exemplo:

```lua
function teste()
    print('hello world')
    print(' esse trecho é executado quando chamamos "teste()" ')
end
```

Depois de definir uma função, basta executar ela como qualquer outro comando:

```lua
> teste()
hello world
 esse trecho é executado quando chamamos "teste()" 
>
```

## Argumentos e retornos

Na matemática, funções tem como característica principal receberem um valor X e devolverem um valor Y.
Em programação quase sempre seguimos o mesmo raciocínio usando argumentos e retornos.

Seguindo essa analogia, podemos passar valores (equivalente ao X) para dentro da função desse modo:

```lua
function duplicado(texto)
    print(texto)
    print(texto)
end
```

Assim, quando chamarmos essa função, passamos o valor que queremos que ```texto``` tenha:

```lua
> duplicado('alguma coisa')
alguma coisa
alguma coisa
> 
```

Já para realizar a o inverso e termos um valor saindo da função (equivalente ao Y), basta usarmos o comando ```return```

```lua
function soma(numero1, numero2)
    return numero1 + numero2
end
```

Desse jeito podemos gravar o valor de saída em uma váriavel ou usar direto em outra função:

```lua
> resultado = soma(1, 2)
> print(resultado)
3
>

> print(soma(1, 2))
3
>
```

## Escopo de váriaveis

Um ponto importante na relação entre uso de váriaveis dentro de funções é o escopo de acesso.
Quando definimos uma váriavel em Lua, por padrão é definida como "[global](https://pt.wikipedia.org/wiki/Vari%C3%A1vel_global)" e isso causa muitos problemas.
Exemplo:

```lua
variavel = 'alguma coisa'

function teste()
    variavel = 'outra coisa'
end
```

Esse código é bem ambíguo e traz muita incerteza do resultado, mas Lua segue o seguinte raciocinio:
  - Gravar 'variavel' com o valor "alguma coisa"
  - Gravar 'teste' com a função:
    - Gravar 'variavel' com o valor "outra coisa"

Nesse ponto, antes de executarmos a função, nossa variavel permanece com o valor original.
Mas caso executemos, seu valor vai ser alterado como definimos pra alterar.

```lua
> print(variavel)
alguma coisa
> teste()
> print(variavel)
outra coisa
> 
```

Isso é um problema gigantesco pois quanto mais variaveis tivermos, mais dificil é manter o controle sobre o valor de cada uma e maior é a chance de sobrepor um valor sem querer e causar problemas.

Como evitamos isso?

Simples, basta mudarmos o escopo em que estamos salvando nossas variaveis usando o comando ```local```.

```lua
variavel = 'alguma coisa'

function teste()
    local variavel = 'outra coisa'
end
```

Assim ao invés de trocarmos o valor da variável original, a função cria uma variável temporária dentro dela qua some assim que a função termina.

```lua
> print(variavel)
alguma coisa
> teste()        
> print(variavel)
alguma coisa
```

Além de evitar conflitos entre uso de variáveis, quando a função encerra e a variável temporária some, a memória que a variável ocupava fica limpa e nosso programa fica mais leve.
Sempre que puder, tente criar apenas variáveis locais e evite ao máximo salvar algo em escopo global.

## Extra

Uma parte engraçada mas que pode ser útil é que funções funcionam como qualquer outro tipo de valor.
Isso significa que outro jeito de definir uma função em Lua é assim:

```lua
printSoma = function(x1, x2) print(x1 + x2) end
```

Que seria o mesmo que escrever:

```lua
function printSoma(x1, x2)
    print(x1 + x2)
end
```

Mas lógico que saber disso trás certas vantagens como callbacks e funções locais.

Exemplo de um callback:

```lua
function soma(x1, x2, callback)
    local resultado = x1 + x2
    callback(resultado)
end
```

Assim podemos escolher qual função callback vai ser através do argumento que passarmos:

```lua
> soma(2, 3, print)
5
```

Isso seria o mesmo que substituir o argumento ```callback``` pelo comando ```print```.
Mas também podemos usar funções próprias como callback:

```lua
function duplicado(valor)
    print(valor)
    print(valor)
end

function soma(x1, x2, callback)
    local resultado = x1 + x2
    callback(resultado)
end
```

```lua
> soma(2, 3, duplicado)
5
5
> 
```

Outra coisa interessante que podemos fazer é criarmos funções locais:

```lua
function teste(x1, x2)
    local function duplicado(valor)
        print(valor)
        print(valor)
    end
    duplicado(x1 + x2)
end
```

Assim a função ```duplicado()``` só existe dentro do escopo da função ```teste()```.

```lua
> teste(3, 4)
7
7
> duplicado('alguma coisa')
stdin:1: attempt to call global 'duplicado' (a nil value)
stack traceback:
        stdin:1: in main chunk
        [C]: ?
> 
```

Próximo:
- [Tabelas](/Basico/tabelas.md)