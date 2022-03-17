## 3.0 Hello World!

Como hábito de qualquer programador iniciante ou avançado ao começar a aprender uma linguagem, começamos com o clássico ["Hello world!"](https://pt.wikipedia.org/wiki/Programa_Ol%C3%A1_Mundo) para então puxarmos temas mais complexos.

Então para escrever nosso primeiro "Hello world!", temos dois modos de fazer isso:
- Através do [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop);
- Ou através de um arquivo .lua com o nosso código.

#### Repl (Read-Eval-Print Loop)
É bem comum que quase todas as linguagens interpretadas tenham esse modo de utilizar, com lua não é diferente. Para entrar nesse modo só precisar executar o interpretador no seu terminal/prompt sem passar nenhum caminho para um arquivo Lua.

Exemplo:
```sh
$ lua
Lua 5.1.5  Copyright (C) 1994-2012 Lua.org, PUC-Rio
> 
```

e dentro desse modo, podemos facilmente testar comandos e trechos curtos de código.

Como nosso "Hello World!":
```lua
> print("Hello World!")
Hello World!
```

#### Arquivos .lua
Claro que para podermos criar códigos mais complexos, é necessário guardar nossa lógica em arquivos bem organizados com nosso código Lua escrito em texto simples. E a principal diferença entre arquivos de texto normais e arquivos de códigos Lua é a extensão .lua no nome do arquivo.

Então se criarmos um arquivo de texto vazio e escrevermos nosso código dentro, teremos um programa Lua pronto para ser executado.

Exemplo em terminal Linux:
```sh
$ echo "print('Hello World')" >> exemplo.lua
$ lua exemplo.lua
Hello World
```

Em Windows, basta abrir com o bloco de notas e salvar com a extensão ".lua" e executar pelo prompt ou powershell no mesmo padrão acima.

Obs: A extensão em casos de scripts que não precisam ser importados, é apenas uma questão de organização estética. É possível rodar o arquivo mesmo se fosse ".txt" ou até que não tivesse extensão.

Próximo: 
- [Variáveis](/Basico/variaveis.md)