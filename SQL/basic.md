# Tutoria SQL - Comandos básicos

<strong>Objetivo:</strong> Mostrar de forma clara e objetiva o uso da linguagem SQL.

<strong>Principais termos técnicos abordados:</strong> 

<strong>Requisitos para as instruções funcionarem:</strong> 

<strong>Requisitos para compreensão das instruções:</strong> 

 Comentários sobre os passos estarão em fonte normal, cor preta.

## Introdução
---

A **Linguagem SQL**(Structured Query Language = Linguagem de consulta estrurada) é a mais utilizada quando o assunto é manipulação de banco de dados.

É implementada em todos os sistemas de bancos de dados relacionais existentes.

---
Você pode criar um arquivo SQL, em praticamente qualquer editor de texto simples, salvando com a extensão <strong>.sql</strong>. Será abordado algumas dicas de ferramentas onde é possível fazer a manipulação de bancos de dados. 

Neste tutorial será abordado o **SQL DDL** (Linguagem de definição de dados), é uma das partes que completam o SQL. É um conjunto de instruções usado para criar e modificar as estruturas dos objetos armazenados no banco de dados.

## Dicas de ferramentas
---

Assim como o próprio github, a linguagem markdonw é suportada por varios outros sites/ferramentas:
1. []()
2. []()
3. []()
4. []()

## Tipos de dados   


|   Tipo   |  Descrição  |    Armazenamento    |
| :---:        |     :---:      |          :---: |
| char(n)        | String de caracteres de tamanho fixo, máximo de 8000 caracteres.             |n             |
| varchar(n)           |String de caracteres de tamanho variável, máximo de 8000 caracteres.                           |n|
|nchar(n)      | Dados unicode de tamanho fixo, máximo de 4000 caracteres.| n|
|nvarchar(n)|Dados unicode de tamanho variável, maximo de 4000 caracteres.| n|
|bit|0, 1 ou nulo| |
|tinyint| Números inteiros de 0 a 255| 1 byte|
|smallint| Números inteiros de -32768 a 32767| 2 bytes|
|int| Números inteiros entre -2,147,483,648 e 2,147,483,647| 4 bytes|
|real|Números de ponto flutuante entre -3,4 x 10³⁸ e 3,4 x 10³⁸| 4 bytes|
|date| data: aaaa/mm/dd||
|time|hora: hh:mm:ss||
|datetime|Combinação de data e hora. Formato: aaaa-mm-dd hh: mm: ss||

## DDL - Data Definition Language - Linguagem de definição de dados  
---

São instruçãoes SQL para criar/alterar/excluir estruturas de um banco de dados. 

São 3 os comandos básicos DDL:

- CREATE 

    Comando utilizado para criar os principais objetos em um banco de dados.

- DROP 

É utilizado para exçlusão de estruturas.

- ALTER

Permite que você altere os atributos de uma determinada tabela ou adicione novos atributos.

## Comandos básicos
---

### 1. CREATE DATABASE

Comando utilizado para criar um novo banco de dados e suas respectivas dependências. 

```CREATE DATABASE db;```

Com esse código é possivel criar um banco de dados chamado "db".

### 2. CREATE TABLE 

Comando utilizado para criar uma nova tabela(é necessário já possuir um banco de dados) com seus respectivos atributos.

```
CREATE TABLE Clientes (
  ClienteCodigo int,
  ClienteNome varchar(20)
); 
```
 
 É criado uma tabela chamada "Clientes" com dois atributos(ClienteCodigo,ClienteNome).

### 3. DROP DATABASE

Comando utilizado para excluir um banco de dados. 

```
DROP DATABASE db;
```

Exclui o banco de dados "db" por completo.


### 4. DROP TABLE

Comando utilizado para excluir uma tabela de um banco de dados.

```
DROP TABLE db.Clientes;
```

Remove a tabela "Clientes" do banco de dados "db";

### 5. ALTER TABLE

Usado para alteração de tabelas já criadas no banco de dados, permitindo que os atributos sejam alterados ou que novos sejam adicionados. 

- Sintaxe:
~~~
ALTER TABLE tabela_nome
ADD atributo tipo_dado
~~~

- Exemplo: 					
~~~	
ALTER TABLE Clientes
ADD idade INT
~~~

O atributo **idade** é adicionado a tabela **Clientes**.

### 6. 

### 7. 

### 8.  

## Para saber mais
--- 
[]() 

[]()

[]()
## Exercícios
---
1. Deveremos propor aqui algum exercisio para a validação da metodologia usada na Tutoria, que tem como proposta DIY ( Do It Yourself ), onde o aluno deverá seguir os passos e no final ele tenha que usar o que foi ensinado para validar o ensino.
