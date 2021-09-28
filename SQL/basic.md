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


1. [MySQL Workbench](https://www.mysql.com/products/workbench/)
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

### Regras de integridade (Constraints) 

São regras aplicadas as colunas de uma tabela, usadas para limitar os tipos de dados que são inseridos, e assim evitam que dados inválidos sejam inseridos no banco.

- **NOT NULL**

    Impede que valores nulos(NULL) sejam inseridos nas colunas de uma tabela, obrigando sempre a possuir um valor.

    - Exemplo
    ```
    CREATE TABLE empregado(
    nome VARCHAR(15) NOT NULL,
	matricula char(9) NOT NULL,
	dataNasc DATE,
	endereco VARCHAR(30)
    );
    ```
    Para o exemplo acima, a constraint **NOT NULL** impede que seja atribuído um valor nulo para os atributos nome e matricula.

- **UNIQUE**

    Usado para garantir que nenhum valor duplicado seja inserido em determinada coluna.

    - Exemplo
        
    ```
    CREATE TABLE empregado(
    ID INT UNIQUE,
    Name VARCHAR(50) NULL
    );
    ```
    Para o exemplo acima, a constraint **UNIQUE** impede que o ID tenha valores duplicados em suas linhas. 

- **PRIMARY KEY**

    Identifica de forma única uma tabela no banco de dados. Não pode possuir valores duplicados e nem conter valores do tipo NULL.  

    - Exemplo

    ```
    CREATE TABLE estudante (
	nome char(15) NOT NULL,
	id-estudante (10) NOT NULL,
	PRIMARY KEY (id-estudante));
    ```

    No exemplo acima, a **chave primária** "id-estudante" referencía toda a tabela "estudante". 

- **FOREIGN KEY**

    Uma chave estrangeira em uma tabela é um campo que aponta para uma chave primária em outra tabela.

    É possível ter mais de uma (ou nenhuma) em uma tabela.

    - Exemplo 1

    Para facilitar a compreensão, usaremos como exemplo duas tabelas: **Pessoa e Moto**. Para montarmos um relacionamento entre elas poderíamos ter na tabela Moto o campo ID_Pessoa fazendo referência à chave primária da tabela Pessoa.

    ```
    CREATE TABLE Moto(
    ID_Moto int PRIMARY KEY AUTOINCREMENT,
    Nome varchar(255),
    Marca varchar(255),
    ID_Pessoa int,
    CONSTRAINT fk_PessoaMoto FOREIGN KEY (ID_Pessoa) REFERENCES Pessoa (ID_Pessoa));
    ```
    **A chave estrangeira foi especificada no CREATE TABLE**

    O campo ```ID_Pessoa``` representa a chave estrangeira, recebendo o valor do campo ```ID_Pessoa```(chave primária na tabela Pessoa) que seria o "dono" da moto.

    - Exemplo 2

    ```
    CREATE TABLE Moto(
    ID_Moto int PRIMARY KEY AUTOINCREMENT,
    Nome varchar(255),
    Marca varchar(255),
    ID_Pessoa int);

    ALTER TABLE Carro
    ADD CONSTRAINT fk_PessoaMoto FOREIGN KEY (ID_Pessoa) REFERENCES Pessoa (ID_Pessoa)
    ```

    O segundo exemplo é idêntico ao primeiro, só muda que a tabela foi criada sem a chave estrangeira. Com o uso do ALTER TABLE é possivel adicionar novas chaves estrangeiras as tabelas do banco de dados.

- **CHECK**


- **DEFAULT**


## Comandos básicos
---

### 1. CREATE DATABASE

Comando utilizado para criar um novo banco de dados e suas respectivas dependências. 

- Sintaxe 
```
CREATE DATABASE nome_bd;
```

- Exemplo

```CREATE DATABASE clientes_db;```

Com esse código é possivel criar um banco de dados chamado "clientes_db".

### 2. CREATE TABLE 

Sintaxe utilizada para criar uma nova tabela(é necessário já possuir um banco de dados) com seus respectivos atributos.

- Sintaxe 
```
CREATE TABLE nome_tabela(
nome_campo_1  tipo_1,
nome_campo_2  tipo_2, 
...
nome_campo_n tipo_n, 
PRIMARY KEY ( campo_x,..));
```
- Exemplo 
```
CREATE TABLE Clientes(
cod_cliente INT NOT NULL AUTO_INCREMENT,
nome VARCHAR (40) NOT NULL,
dt_nasc DATE,
contato CHAR (11),
PRIMARY KEY (cod_cliente));
```
 
É criado uma tabela chamada "Clientes" com quatro atributos(cod_cliente, nome, dt_nasc, contato). 

No exemplo acima vimos a seguinte declaração na criação da tabela:

```
PRIMARY KEY (cod_cliente);
```

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

#### 5.1 ADD

1. Pode-se utilizar a cláusula ADD para adicionar novos campos a uma tabela. 

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

2. É possível **adicionar uma chave primária** com o comando ADD.

    - Exemplo 
    ```
    ALTER TABLE Clientes
    ADD PRIMARY KEY(nome);
    ```

3. É possível eliminar uma coluna com os comandos ALTER e DROP

    - Exemplo
    ```
    ALTER TABLE Nome_Tabela
    DROP nome_campo;
    ```
    Alguns SGBD'S utilizando o comando CROP COLLUMN ao invés de somente drop.

4. Pode-se mudar o nome da respectiva tabela com o comando **rename to**
    
    - Exemplo
    ```
    ALTER TABLE Clientes
    rename to novo_Nome_Da_Tabela;
    ```

#### 5.2 MODIFY

É possível utilizar o comando MODIFY para alterar o tamanho dos campos que já foram definidos. Por exemplo: no atributo nome que foi definido com tamanho 40 e deve ser aumentado para 60. 

- Exemplo
```
ALTER TABLE Clientes
MODIFY nome(60);
``` 

## Para saber mais
--- 
[]() 

[]()

[]()
## Exercícios
---
1. Deveremos propor aqui algum exercisio para a validação da metodologia usada na Tutoria, que tem como proposta DIY ( Do It Yourself ), onde o aluno deverá seguir os passos e no final ele tenha que usar o que foi ensinado para validar o ensino.
