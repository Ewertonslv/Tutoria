## DML - Data Manipulation Language- Linguagem de manipulação de dados
---
Neste tutorial será abordado o **SQL DML** (Linguagem de manipulação de dados), é uma das partes que completam o SQL. É um conjunto de instruções utilizado para a recuperação, inclusão, remoção e modificação de informações em bancos de dados.

São 4 os comandos básicos DML:

- Insert

Comando utilizado para inserir informações em um banco de dados.

- Update

Comando utilizado para fazer alterações em um banco de dados.

- Delete

Comando utilizado para fazer a remoção de informações em um banco de dados.

- Select

Comando utilizado para fazer uma seleção de informações em um banco de dados.

### 1. INSERT

- Sintaxe:

```SQL
INSERT INTO NOME_TABELA(atributos) VALUES(valores_atributos);
```

- Exemplo: 

```SQL
INSERT INTO Aluno(cod_aluno, nome, endereco) VALUES(1, ‘Ewerton’, ‘Rua sem entrada');
```
 
 ### 2. UPDATE

 - Sintaxe

 ```SQL
UPDATE TABELA_NOME SET column1 = value1, column2 = value2,... 
WHERE condicao;
 ```

- Exemplo

```SQL
UPDATE livros SET disponivel = 1 WHERE id = 10;
```

Atribui o valor "1" para a coluna "disponivel" onde o código do livro é 10.

 ### 3. DELETE

 - Sintaxe

 ```SQL
 DELETE FROM TABELA_NOME WHERE condicao;
 ```

- Exemplo

```SQL
DELETE FROM livros WHERE nome = 'Chapeuzinho vermelho';
```

Exclui a linha onde está o livro "Chapeuzinho vermelho".

### 4. SELECT

 - Sintaxe

 ```SQL
 
 ```

- Exemplo

```SQL

```

