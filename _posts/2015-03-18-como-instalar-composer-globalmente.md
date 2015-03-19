---
title: "Como instalar composer globalmente no ubuntu"
---

O genki desu ka? Aqui é Rubens Fernandes trazendo um simples post de como instalar o ***composer*** globalmente, direto ao assunto, no ***terminal*** (ctrl+alt+t) digite:

```sh
$ curl -sS https://getcomposer.org/installer | php 
```

Depois disso você precisa mover o composer.phar que acabou de baixar para a pasta ***bin*** do sistema assim você executar ele de qualquer lugar sem precisar escrever **php composer.phar** digite:

```sh
$ mv composer.phar /usr/local/bin/composer 
```

Note que renomeamos o ***composer.phar*** para ***composer*** assim não precisamos mais usar o php para executar o script pelo terminal, o sistema reconhece e executa automaticamente.

Agora é só usar de qualquer lugar via terminal experimente:

```sh
$ composer install
$ composer update
$ composer --self-update
```

Até a proxima :coffee: