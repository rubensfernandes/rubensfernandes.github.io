# Fazendo deploy de um projeto MEAN para uma VPS
Rode os comandos abaixo sempre na raiz onde seus repositórios ficarão

#### Criar um repositório vazio na VPS

```
git init nomedorepo.git --bare
```

#### Criar a pasta dentro do server

```
mkdir /var/www/nomedorepo
```

#### Configura o post-receive

No repositório que acabamos de iniciar edite o arquivo post-receive ou crie-o se não existir:

```
nano nomedorepo.git/hooks/post-receive
```

Insira as linhas abaixo nele editando conforme necessário

```
#!/bin/sh
GIT_WORK_TREE=/pasta/onde/ficarao/os/arquivos/nomedorepo git checkout -f master
```
Precione CRTL+O depois de um ENTER para gravar alterações (se estiver usando o 'nano' para editar)

De permissão de execução para o script criado
```
chmod +x nomedorepo.git/hooks/post-receive
```
#### Adicionar como um remote esse repositório que acabamos de criar no seu repositório local
```
git remote add nomedoremote usuario@urldoservidor.com.br:~/nomedorepo.git
```

#### Envia todos os arquivos do repositório local para a VPS no novo remote que acamos de configurar
```
git push nomedoremote --all
```

