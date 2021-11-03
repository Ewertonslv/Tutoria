## Tutorial algebra relacional

- A Álgebra Relacional é uma linguagem de consulta formal e procedural, ou seja, o usuário dá as instruções ao sistema para que o mesmo realize uma seqüência de operações na base de dados para calcular o resultado desejado.

- Possui como entrada uma ou duas relações e retorna, como resultado, um nova relação. 

- Principais conceitos:

    1. Uma linha é chamada de tupla;
    2. O cabeçalho da coluna é chamado de atributo;
    3. Tabela é chamada de relação;
    4. O tipo de dados que descreve os tipos de valores que podem aparecer em cada coluna é chamado de domínio;
    5. A álgebra relacional é uma forma de cálculo sobre conjuntos ou relações.  

### Quadro de operadores

|   Operação   |  Símbolo  |    Descrição    |
| :---         |     :---:      |          :--- |
| Projeção           | π ("Pi")              | π < Lista de campos > (tabela)            |
| Seleção/Restrição           | σ ("Sigma")             | σ < Condição de seleção>            |
|União|∪|(Tabela 1) ∪(Tabela 2)|
|Intersecção|∩ |(Tabela 1) ∩ (Tabela 2)|
|Diferença|-|(Tabela 1) - (Tabela 2)|
|Produto cartesiano|X|(Tabela 1) X (Tabela 2|
|Junção|&#124;X&#124;|(Tabela 1) &#124;X&#124;< condição de junção > (Tabela 2)|
|Divisão|÷ |(Tabela 1) ÷ (Tabela )|
|Renomeação|ρ ("rho")| ρ Nome(Tabela)|
|Atribuição|↤|Variável ↤ Tabela|

### Comparadores 

|   Operador   |    Símbolo    |
|    :---:     |     :---:      |     
| Igual a          | =             | 
|Menor que|<|
|Maior que|>|
|Menor ou igual a|<=|
|Maior ou igual a|>=|
|Diferente||
|"e" lógico|^|
|"ou" lógico|V|
|Não||


**Relação** = Tabela, entidade, na terminologia formal de banco de dados.

**Tupla** = Linha da tabela, registro, na terminologia formal de banco de dados.

### 1. Seleção 

- Sintaxe

```σ<condição de seleção>(<Relação>)```

Condição: < atributo > < op > < constante > ou < atributo > < op > < atributo > 

< op > = {=, >, <, ≤, ≥, ≠}

Na condição pode ser utilizado os conectivos booleanos AND, OR e NOT. 

**Tabela Alunos**

Alunos (id, nome, sexo)
|id	|nome	|sexo|
|:---: |:----:| :----:|
|1| 	Manoel|	M|
|2 	|Jasmin	|F|
|3	|Augusto|	M|
|4	|Janete	|F|

**Ex1.** Selecione as tuplas de alunos onde nome = Augusto

**σnome = 'Augusto' (Alunos)**

- Resultado: 

|id	|nome	|sexo|
|:---: |:----:| :----:
|3	|Augusto|	M|

**Ex2.** Selecione as tuplas de Alunos com 4 < id > 1

**σid > 1 ^ id < 4(Alunos)**

- Resultado:

|id	|nome	|sexo|
|:---: |:----:| :----:
|2 	|Jasmin	|F|
|3	|Augusto|	M|
### 2. Projeção 

- Sintaxe

```π <LISTA DE ATRIBUTOS>(Relação)```

### 3. União 

- Sintaxe

```Relação1 ∪ Relação2 ( R1 ∪ R2)```

### 4. Intersecção

- Sintaxe

```relação1 ∩ relação2 ( R1 ∩ R2 )```

### 5. Diferença 

- Sintaxe

```relação1 - relação2 ( R1 - R2 )```

### 6. Produto cartesiano

- Sintaxe

```relação1 x relação2 ( R1 x R2 )```

### 7. Junção

- Sintaxe

```relação1 |x|<condição de junção> relação2```

### 8. Divisão 

- Sintaxe

```relação1 ÷ relação2```


### 9. Renomeação 

- Sintaxe


```ρ<novo nome> (relação)```


### 10. Atribuição 

- Sintaxe

```variável ↤ relação```
