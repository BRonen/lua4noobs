## 3.1 Variáveis

Um dos temas mais básicos em programação são as [variáveis](https://pt.wikipedia.org/wiki/Vari%C3%A1vel_(programa%C3%A7%C3%A3o)). Em resumo, são um jeito de gravar valores (dados) e chamar através de nomes.

Exemplo:
```lua
> nome = 'Nome de alguem'
```

Para conseguirmos ler o valor que gravamos dentro dessa variáveis, podemos usar o comando ```print()```. Esse comando é, resumidamente, um jeito de escrever um valor no terminal onde executamos nosso código. Já vimos ele no [Hello World](/Basico/hello-world.md) e vamos usar com bastante frequência daqui pra frente.

```lua
> nome = 'Nome de alguem'
> print(nome)
Nome de alguem

> nome = 'Mudando de nome'
> print(nome)
Mudando de nome
```

Também podemos usar variáveis para trabalhar com números

```lua
> numero = 10
> print(numero)
10

> numero = numero + 1
> print(numero)
11
> numero = numero * 2
22
```

O valor da variável "numero" constantemente muda de acordo com o que dizemos pra ela guardar, isso vai ser um conceito muito útil quando começarmos a ver [laços de repetição](/Basico/lacos-repeticao.md).

### Tipos de variáveis

Até agora só lidamos com dois tipos de dados dentro dos nossos códigos, dentro de lua podemos achar 8 tipos de valores. A forma com que trabalhamos com cada tipo de dado é um pouco diferente, os únicos que vimos até agora foram [string](https://www.lua.org/pil/2.4.html) e [number](https://www.lua.org/pil/2.3.html) mas abaixo tem uma descrição curta dos tipos mais comuns.

|   Tipo                                    | Descrição                   |
|:-----------------------------------------:|-----------------------------|
|  [number](/Basico/tipos/number.md)        | Números inteiros e decimais |
|  [boolean](/Basico/tipos/boolean-nil.md)  | Verdadeiro ou falso         |
|  [nil](/Basico/tipos/boolean-nil.md)      | Representa um valor vazio   |
|  [string](/Basico/tipos/string.md)        | Conjunto de texto           |
|  [function](/Basico/funcoes.md)          | Trecho de código            |
|  [table](/Basico/tabelas.md)               | Conjunto de variáveis       |

Por enquanto não recomendo travar muito tentando entender como cada tipo funciona pois veremos com calma ao longo de outros temas e você poderá voltar aqui e ler sobre cada um pra entender melhor.

#### Dicas
Mesmo que seja cedo pra explicar, é bom ter em mente um certo cuidado ao nomear variáveis. Por serem um recurso de uso extremamente frequente, muitos nomes podem se misturar dentro do seu código. Saber usar nomes bem descritivos ajuda muito a tornar o código mais legível e bem organizado.

Existem diversos debates sobre nomeclatura e coisas assim mas não pretendo entrar muito a fundo, mas recomendo manter o código sempre o [mais limpo](https://letmegooglethat.com/?q=clean+code) possível.

Próximo: 
- [Operadores](/Basico/operadores.md)