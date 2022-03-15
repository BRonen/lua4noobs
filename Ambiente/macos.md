## 2.2 Configuração de ambiente: Linux

O modo mais simples de instalar seria através de um [package manager](https://pt.wikipedia.org/wiki/Sistema_gestor_de_pacotes) como o [Homebrew](https://brew.sh/) mas também é possível compilar manualmente tendo o Xcode instalado.

### Usando Homebrew
```sh
$ brew update
$ brew install lua
```

### Compilar manualmente
```sh
$ wget http://www.lua.org/ftp/lua-5.1.5.tar.gz
$ tar -zxf lua-5.1.5.tar.gz
$ cd lua-5.1.5
$ sudo make install
```

Próximo: 
- [Hello World](/Basico/hello-world.md)