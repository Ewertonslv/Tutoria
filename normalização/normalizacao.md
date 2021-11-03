## Tutorial de Normalização

Normalização é um processo de aplicação de normas técnicas, que tem como intuito a prevenção de erros, evitando redundâncias, e possíveis inconsistências nas informações. Além disso, ajuda na criação e manutenção do sistema.

Existem até 5 formas de normalização, mas as 3 primeiras são as mais comuns:

### NF1 - Primeira forma de normalização 
A primeira forma é a repetição de chave primária. Uma relação obedece a primeira forma normal se todos os seus atributos forem simples e monovalorados, ou seja, o CPF de uma pessoa. É um número que nunca se repete.

Para uma tabela com atributos repetidos, deve-se criar uma nova tabela com a chave primária da tabela anterior. Fazendo com que predomine apenas um valor por campo. 

| Código | Nome |Endereço| Telefone|
| :---: | :---:| :---:| :---:|
|1  | Ewerton Silva  | Rua de cima 123 centro|31903290323 31903247890|
|2  | Manoel Fernandes   | Rua de baixo 321 Centro|   31290482300  31298473627|


No exemplo acima podemos perceber dois erros:
1. Uma pessoa com dois números de telefone
2. Endereço multivalorado(rua e bairro)

O procedimento a ser feito é a criação de uma nova tabela com novas colunas para os respectivos atributos multivalorados:

| Código | Nome |Endereço| Bairro|
| :---: | :---:| :---:| :---:|
|1  | Ewerton Silva  | Rua de cima 123 | Centro|
|2  | Manoel Fernandes   | Rua de baixo 321 |   Centro|

Com isso, a tabela acima encontra-se na primeira forma normal. Mas, para a coluna com mais de um atributo:

|Código|Telefone|
|:---:|:---:|
|1|31903290323|
|1|31903247890|
|2|31290482300|
|2|31298473627|

Com isso as tabelas ficam na primeira forma normal.


### NF2 - Segunda forma de normalização 
Para estar na segunda forma normal, primeiramente deve estar na primeira forma normal. 

Após isso, todos os atributos (exluso a chave) devem ser totalmente dependentes da chave primaria. Evitando assim, redundâncias no banco de dados.

| id_locacao | id_filme |nome_filme| dt_devolucao|id_cliente |
| :---: | :---:| :---:| :---:| :---: |
|010  | 01  | O Rei Leão|03/12/2021|001|
|020  | 02   | Poderoso Chefão|  05/12/2021 |002|
|030| 03|O Senhor dos Anéis|04/12/2021|003|

No exemplo acima podemos perceber que "nome_filme" está associado a "id_filme" assim como "id_locacao", causando uma redundância no banco de dados. Tornando-se um valor que não depende apenas da chave primária.

O procedimento a ser feito é a criação de uma nova tabela apenas com o nome dos filmes, e seus respectivos códigos. Utilizando o recurso de chave estrangeira para possíveis consultas futuramente. 

|id_filme|nome_filme|
|:---:|:---:|
|01|O Rei Leão|
|02|Poderoso Chefão|
|03|O Senhor dos Anéis|

E a tabela original "perderia" a coluna "nome_filme". Com isso, todos os valores dependeriam apenas da chave.

| id_locacao | id_filme | dt_devolucao|id_cliente |
| :---: | :---:| :---:| :---: |
|010  | 01  |03/12/2021|001|
|020  | 02  |  05/12/2021 |002|
|030| 03|04/12/2021|003|

Com isso, a tabela estar na segunda forma normal. 

### NF3 - Terceira forma de normalização 

Para estar na terceira forma normal, precisa estar na primeira e na segunda forma normal. 

Após colocada na segunda forma normal, a tabela não pode ter um atributo **(não-chave)** que determina outro atributo. Ou seja, não pode haver uma dependência transitiva de um atributo não-chave sobre a chave primaria.

Dependêndia transitiva é uma dependência entre dois ou mais atributos não-chave.

