## 2.1 Configuração de ambiente: Linux

O interpretador de lua está presente nos repositórios oficiais de diversas distros Linux mas também é possível baixar o código fonte e compilar manualmente.

### Debian e derivados
```sh
$ sudo apt install lua5.1
```

### Compilar manualmente
```sh
$ curl -R -O http://www.lua.org/ftp/lua-5.1.5.tar.gz
$ tar -zxf lua-5.1.5.tar.gz
$ cd lua-5.1.5
$ sudo make install
```

Próximo: 
- [Hello World](/Basico/hello-world.md)