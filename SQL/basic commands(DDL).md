## DDL - Data Definition Language - Linguagem de definição de dados  
---
Neste tutorial será abordado o **SQL DDL** (Linguagem de definição de dados), é uma das partes que completam o SQL. É um conjunto de instruções usado para criar e modificar as estruturas dos objetos armazenados no banco de dados.

São 3 os comandos básicos DDL:

- CREATE 

Comando utilizado para criar os principais objetos em um banco de dados.

- DROP 

É utilizado para exçlusão de estruturas.

- ALTER

Permite que você altere os atributos de uma determinada tabela ou adicione novos atributos.

### 1. CREATE DATABASE

Comando utilizado para criar um novo banco de dados e suas respectivas dependências. 

- Sintaxe 
```SQL
CREATE DATABASE nome_bd;
```

- Exemplo

```SQL
CREATE DATABASE clientes_db;
```

Com esse código é possivel criar um banco de dados chamado "clientes_db".

### 2. USE DATABASE
Após criar o banco de dados precisa informar ao SGBD que quer utilizar aquele banco, senão fizer isso, todos os comandos executados serãm criados no database padrão do SGBD. 

- Sintaxe

```SQL
USE DATABASE nome_db;
```

- Exemplo

```SQL
USE DATABASE nome_bd;
```

### 3. CREATE TABLE 

Sintaxe utilizada para criar uma nova tabela(é necessário já possuir um banco de dados) com seus respectivos atributos.

- Sintaxe 

```SQL
CREATE TABLE nome_tabela(
nome_campo_1  tipo_1,
nome_campo_2  tipo_2, 
...
nome_campo_n tipo_n, 
PRIMARY KEY ( campo_x,..));
```

- Exemplo 

```SQL
CREATE TABLE Clientes(
cod_cliente INT NOT NULL AUTO_INCREMENT,
nome VARCHAR (40) NOT NULL,
dt_nasc DATE,
contato CHAR (11),
PRIMARY KEY (cod_cliente));
```
 
É criado uma tabela chamada "Clientes" com quatro atributos(cod_cliente, nome, dt_nasc, contato). 

No exemplo acima vimos a seguinte declaração na criação da tabela:

```SQL
PRIMARY KEY (cod_cliente);
```

### 4. DROP DATABASE

Comando utilizado para excluir um banco de dados. 

```SQL
DROP DATABASE db;
```

Exclui o banco de dados "db" por completo.


### 5. DROP TABLE

Comando utilizado para excluir uma tabela de um banco de dados.

```SQL
DROP TABLE nome_tabela;
```

### 6. ALTER TABLE

Usado para alteração de tabelas já criadas no banco de dados, permitindo que os atributos sejam alterados ou que novos sejam adicionados. 

#### 6.1 ADD

1. Pode-se utilizar a cláusula ADD para adicionar novos campos a uma tabela. 

    - Sintaxe:

    ~~~SQL
    ALTER TABLE tabela_nome
    ADD atributo tipo_dado
    ~~~

    - Exemplo: 		

    ~~~	SQL
    ALTER TABLE Clientes
    ADD idade INT
    ~~~

    O atributo **idade** é adicionado a tabela **Clientes**.

2. É possível **adicionar uma chave primária** com o comando ADD.

    - Exemplo 

    ```SQL
    ALTER TABLE Clientes
    ADD PRIMARY KEY(nome);
    ```

3. É possível eliminar uma coluna com os comandos ALTER e DROP

    - Exemplo

    ```SQL
    ALTER TABLE Nome_Tabela
    DROP nome_campo;
    ```
    Alguns SGBD'S utilizando o comando CROP COLLUMN ao invés de somente drop.

4. Pode-se mudar o nome da respectiva tabela com o comando **rename to**
    
    - Exemplo

    ```SQL
    ALTER TABLE Clientes
    rename to novo_Nome_Da_Tabela;
    ```

#### 6.2 MODIFY

É possível utilizar o comando MODIFY para alterar o tamanho dos campos que já foram definidos. Por exemplo: no atributo nome que foi definido com tamanho 40 e deve ser aumentado para 60. 

- Exemplo

```SQL
ALTER TABLE Clientes
MODIFY nome(60);
``` 

Também é possível alterar o tipo de um campo. Supondo que precisasse mudar atributo "nome" do tipo varchar para apenas char.

- Exemplo

```SQL
ALTER TABLE Clientes
MODIFY nome CHAR(100);
``` 

## Para saber mais
--- 
[]() 

[]()

[]()

## Exercícios
---

#### 1. Criem um novo esquema de BD.

- Crie um banco chamado empresa_db

- Dentro dele crie três tabelas:

1. **Funcionario** (codigo, nome, endereco, telefone,
cod_departamento)
cod_departamento referencia Departamento

2. **Departamento** (codigo, descricao)

3. **Dependentes** (codigo, cod_funcionario, nome,
data_nasc)

    cod_funcionario referencia Funcionario
    