## Tutorial de Normalização

Normalização é um processo de aplicação de normas técnicas, que tem como intuito a prevenção de erros, evitando redundâncias, e possíveis inconsistências nas informações. Além disso, ajuda na criação e manutenção do sistema.

Existem até 5 formas de normalização, mas as 3 primeiras são as mais comuns:

### NF1 - Primeira forma de normalização 
A primeira forma é a repetição de chave primária. Uma relação obedece a primeira forma normal se todos os seus atributos forem simples e monovalorados, ou seja, o CPF de uma pessoa. É um número que nunca se repete.

Para uma tabela com atributos repetidos, deve-se criar uma nova tabela com a chave primária da tabela anterior. Fazendo com que predomine apenas um valor por campo. 

imagem aqui

No exemplo acima podemos perceber dois erros:
1. Uma pessoa com dois números de telefone
2. Endereço multivalorado(rua e bairro)

O procedimento a ser feito é a criação de uma nova tabela com novas colunas para os respectivos atributos multivalorados.


### NF2 - Segunda forma de normalização 
Primeiramente deve estar na primeira forma normal. 

### NF3 - Terceira forma de normalização 


