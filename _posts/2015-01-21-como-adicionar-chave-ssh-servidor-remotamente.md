---
title: "Como adicionar uma chave SSH diretamente no servidor via linha de comando"
---

Antes vamos gerar nossa chave SSH caso você já possua ignore está etapa.
Vão aparecer várias perguntas durante este comando, o mais importante é preencher corretamente o email, se quiser deixe sem senha quando for solicitado, caso contrário cada vez que você for logar no servidor ele vai pedir a senha da tua chave.

``` ssh-keygen -t rsa ```


Depois de gerada a chave verifique se ela foi criada corretamente:

``` cat ~/.ssh/id_rsa.pub ```

Se apareceu na tela uma sequência de caracteres e seu email ou nome do seu computador no final está tudo ok, agora digite o seguinte comando:

```cat ~/.ssh/id_rsa.pub | ssh user@hostname 'cat >> .ssh/authorized_keys' ```

Pronto agora quando você for acessar o servidor via SSH você não necessitará mais colocar uma senha.

:coffee:
