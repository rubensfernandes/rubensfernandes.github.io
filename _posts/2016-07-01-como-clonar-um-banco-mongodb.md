---
title: "Como clonar um banco de dados no MongoDB"
---

Suponhamos que você precise fazer com que a database de nome **banco1** seja duplicada para **banco2** dentro do seu servidor local ou externo siga os seguintes passos:

1. Primeiro logue no servidor ou se for sua máquina local passe para o próximo passo:

	``` ssh user@servidor.com.br```

2. Para criar um backup do **banco1** rode:

	``` mkdir ~/temp && cd ~/temp ```

	> esse comando é opcional, fiz isso só por questões de organização, ele vai criar uma pasta chamada **temp** e vai ir até ela pela linha de comando.

	``` mongodump -d banco1 -o pasta_para_salvar ```

	> esse comando gera um backup do seu banco1 na pasta 'pasta_para_salvar', se você rodar um **ls** vai ver que ele criou uma pasta com o nome especificado em **-o** se o **-o** não for especificado ele vai gerar o backup na pasta **dump**

3. Para importar esse backup para o **banco2** rode:
	
	``` mongorestore -d banco2 pasta_para_salvar/banco1 ```

	> note que é essencial passar o nome da pasta que usou em **-o** na hora de gerar o backup, usamos ***pasta_para_salvar*** nesse exemplo.

4. Logue no seu mongodb e veja se a nova database foi criada com sucesso:

	``` mongo ```

	> o próximo comando deve ser rodados no shell do mongodb.

	``` > show dbs ```

	> você deve ver algo como: 
	```
	banco1	0.000GB
	banco2	0.000GB
	local   0.000GB
	```

Pronto agora você possui uma cópia do banco1 no banco2.

:coffee:
