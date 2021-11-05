# Tutoria SQL - Introdução

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
Você pode criar um arquivo SQL em praticamente qualquer editor de texto simples, salvando com a extensão ```.sql```. 

![](https://github.com/Ewertonslv/Tutoria/blob/main/SQL/imagens/sqlimage.png
)

## Bancos de dados mais famosos:
---

1. [postgresql](https://www.postgresql.org/)
2. [Oracle](https://www.oracle.com/br/index.html)
3. [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)
4. [MySQL](https://www.mysql.com/)
5. [MariaDB](https://mariadb.org/)

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

### Cláusulas

➤ **FROM** - utilizada para especificar a tabela que se vai selecionar os registros.

➤ **WHERE** - utilizada para especificar as condições que devem reunir os registros que serão selecionados.

➤ **GROUP BY** - utilizada para especificar as condições que devem reunir os registros que serão selecionados.

➤ **HAVING** - utilizada para expressar a condição que deve satisfazer cada grupo.

➤ **ORDER BY** - utilizada para ordenar os registros selecionados com uma ordem específica.
- Divide-se em dois: 

    - **Modo ascendente (ASC)** - Ordena os valores do menor para o maior. É o padrão do ORDER BY. Portanto, nem é necessário estar explicito no comando. 

    - **Modo descendente (DESC)** - Ordena os valores do maior para o menor. Diferente do comando ASC, ele deve ser explícito.


➤ **DISTINCT** - utilizada para selecionar dados sem repetição.

➤ **JOIN** - utilizada para juntar duas tabelas a partir de condições de combinação de registros.

➤ **UNION** - combina os resultados de duas consultas SQL em uma única tabela para todas as linhas correspondentes.

### Operadores aritméticos 


|   Operador   |   Significado    |
|    :---:     |        :---:     |
| *         |   Multiplicação   |
|+          | Soma              |
|-          |Subtração          |
|/          |Divisão            |


### Operadores de comparação

|   Operador   |  Símbolo  |    Significado    |
|    :---:     |     :---:      |     :---:     |
| Igual a          | =             | Retorna verdadeiro caso o primeiro valor seja igual ao segundo.           |
| Diferente de     | <>             | Retorna verdadeiro caso o primeiro valor seja diferente do segundo.           |
|Menor que|<|Retorna verdadeiro caso o primeiro valor seja menor que o segundo.|
|Maior que|>|Retorna verdadeiro caso o primeiro valor seja maior que o segundo.|
|Menor ou igual a|<=|Retorna verdadeiro caso o primeiro valor seja menor ou igual ao segundo.|
|Maior ou igual a|>=|Retorna verdadeiro caso o primeiro valor seja maior ou igual ao segundo.|

### Regras de integridade (Constraints) 

São regras aplicadas as colunas de uma tabela, usadas para limitar os tipos de dados que são inseridos, e assim evitam que dados inválidos sejam inseridos no banco.

➤ **NOT NULL**

Impede que valores nulos(NULL) sejam inseridos nas colunas de uma tabela, obrigando sempre a possuir um valor.

- Exemplo
    ```SQL
    CREATE TABLE empregado(
    nome VARCHAR(15) NOT NULL,
	matricula char(9) NOT NULL,
	dataNasc DATE,
	endereco VARCHAR(30));
    ```
Para o exemplo acima, a constraint **NOT NULL** impede que seja atribuído um valor nulo para os atributos nome e matricula.

➤ **UNIQUE**

Usado para garantir que nenhum valor duplicado seja inserido em determinada coluna.

- Exemplo
        
    ```SQL
    CREATE TABLE empregado(
    ID INT UNIQUE,
    Name VARCHAR(50) NULL;
    ```
Para o exemplo acima, a constraint **UNIQUE** impede que o ID tenha valores duplicados em suas linhas. 

➤ **PRIMARY KEY**

Identifica de forma única uma tabela no banco de dados. Não pode possuir valores duplicados e nem conter valores do tipo NULL.  

- Exemplo

    ```SQL
    CREATE TABLE estudante (
	nome char(15) NOT NULL,
	id_estudante (10) NOT NULL,
	PRIMARY KEY (id_estudante));
    ```

No exemplo acima, a **chave primária** "id_estudante" referencía toda a tabela "estudante". 


➤ **FOREIGN KEY**

Uma chave estrangeira em uma tabela é um campo que aponta para uma chave primária em outra tabela.

É possível ter mais de uma (ou nenhuma) em uma tabela.

- Exemplo 1

Para facilitar a compreensão, usaremos como exemplo duas tabelas: **Pessoa e Moto**. Para montarmos um relacionamento entre elas poderíamos ter na tabela Moto o campo ID_Pessoa fazendo referência à chave primária da tabela Pessoa.


~~~SQL
CREATE TABLE Moto(
ID_Moto int PRIMARY KEY AUTOINCREMENT,
Nome varchar(255),
Marca varchar(255),
ID_Pessoa int,
CONSTRAINT fk_PessoaMoto FOREIGN KEY (ID_Pessoa) REFERENCES Pessoa (ID_Pessoa));
~~~

**A chave estrangeira foi especificada no CREATE TABLE**

O campo ```ID_Pessoa``` representa a chave estrangeira, recebendo o valor do campo ```ID_Pessoa```(chave primária na tabela Pessoa) que seria o "dono" da moto.

- Exemplo 2

    ```SQL
    CREATE TABLE Moto(
    ID_Moto int PRIMARY KEY AUTOINCREMENT,
    Nome varchar(255),
    Marca varchar(255),
    ID_Pessoa int);

    ALTER TABLE Carro
    ADD CONSTRAINT fk_PessoaMoto FOREIGN KEY (ID_Pessoa) REFERENCES Pessoa (ID_Pessoa);
    ```

O segundo exemplo é idêntico ao primeiro, só muda que a tabela foi criada sem a chave estrangeira. Com o uso do ALTER TABLE é possivel adicionar novas chaves estrangeiras as tabelas do banco de dados.

➤ **CHECK**

É utilizada para definir um intervalo de valores que podem ser inseridos nas colunas. A restição CHECK avalia os valores modificados e inseridos e se satisfazer a condiçao eles são inseridos na tabela. 

- Exemplo

    ```SQL
    CREATE TABLE empregado(
    id INT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    salario INT CHECK (salario > 0));
    ```

Para o exemplo acima, o campo salário só aceitará valores maiores que 0. Caso contrário, qualquer outro valor fornecido será rejeitado. 

➤ **DEFAULT**

É utilizado para inserir um valor padrão em uma coluna da tabela. Ele é inserido automaticamente nos registros, se nenhum outro valor for especificado.

- Exemplo 
	
    ```SQL
    CREATE TABLE empregado(
    id INT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    endereco VARCHAR(50) DEFAULT ‘São Paulo’)
    ```
	
Define São paulo como valor padrão para o atributo "endereco".
     
Para **remover o valor padrão** basta fazer um ALTER TABLE sem a restrição DEFAULT no campo em que havia sido atribuído.
     
- Exemplo 
     
     ```SQL
     ALTER TABLE empregado
     MODIFY COLUMN endereco Varchar(50);
     ```


## Para saber mais
--- 
[]() 

[]()

[]()

## Exercícios
---
1. Deveremos propor aqui algum exercisio para a validação da metodologia usada na Tutoria, que tem como proposta DIY ( Do It Yourself ), onde o aluno deverá seguir os passos e no final ele tenha que usar o que foi ensinado para validar o ensino.
