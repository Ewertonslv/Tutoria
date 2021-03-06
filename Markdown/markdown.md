# Tutoria Markdown

<strong>Objetivo:</strong> Mostrar de forma clara e objetiva o uso da linguagem Markdown.

<strong>Principais termos técnicos abordados:</strong> Markdonw, Visual Studio Code.

<strong>Requisitos para as instruções funcionarem:</strong> Ter acesso ao GitHub ou algum outro site/ferramenta que será apresentado mais a frente. 

<strong>Requisitos para compreensão das instruções:</strong> 

 Comentários sobre os passos estarão em fonte normal, cor preta.

## Introdução
---
Você pode criar um arquivo markdown, em praticamente qualquer editor de texto simples, salvando com a extensão <strong>.md</strong>. Será abordado algumas dicas de ferramentas e sites que suportam Markdonw.  

## Dicas de ferramentas
Assim como o próprio github, a linguagem markdonw é suportada por varios outros sites/ferramentas:
1. [Bitcuket](https://bitbucket.org/)
2. [Stackoverflow](https://stackoverflow.com/)
3. [Reddit](https://www.reddit.com/)
4. [SourceForge](https://sourceforge.net/)

Além desses sites, o [Visual Studio Code](https://code.visualstudio.com/) possui uma extenção que permite uma visualização rápida do que está sendo digitado:

![Markdown preview Github Styling](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/exten%C3%A7%C3%A3o_markdonw_para_vs_code.PNG)

[Markdown preview Github Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)




## Comandos básicos 
---

### 1. Titulos
Para marcar um título, você vai usar ```#``` a quantidade de vezes que irá representar o nível do título. Exemplo:

```
# Título 1 
## Título 2 
### Título 3 
#### Título 4 
##### Título 5
###### Título 6
```
Resultado: 

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/titulo_result.PNG)

### 2. Parágrafos e quebras de linha
Para gerar parágrafos, basta você escrever o texto em uma linha:
```
Este é um parágrafo.
  
Este é outro parágrafo.
```

### 3. Negrito
```
**Este texto está em negrito**
```

Resultado: 

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/negrito_result.PNG)

### 4. Itálico
```
*Este texto está em itálico*
```

Resultado:

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/result_italico.PNG)

### 5. Links

Para gerar links, você usa ```[Texto](Link)```. Dentro dos colchetes você coloca o texto do link, e dentro dos parênteses, você coloca a URL:

```
[Github](https://github.com/)
```

### 6. Links automáticos
Se o texto do seu link é o próprio link, você pode envolvê-lo entre ```<``` e ```>```, que o link será gerado automaticamente:

```
<https:https://github.com/>
```
### 7. Imagens
Semelhante ao código para inserir um link, adicionando um ponto de exclamação ```!``` no inicio do código:

```
![Título da imagem](URL da imagem)
```

### 8. Tabelas 

Você pode criar tabelas com barras verticais ```|``` e hifens ```-```. Os hifens são usados para criar o cabeçalho das colunas e as barras verticais, para separar as colunas:

```
| Cabeçalho 1| Cabeçalho 2|
|------------|------------|
|     x      |     z      |
|     y      |     h      |
```
Resultado: 

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/tabela1_result.png
)

As barras verticais em cada extremo da tabela são opcionais.

As células podem ter largura variada e não precisam estar alinhadas perfeitamente com as colunas. Deve ter no mínimo três hifens em cada coluna da linha do cabeçalho.

```
| Comando | Descrição |
| --- | --- |
| git status | Lista de todos os arquivos modificados ou novos |
| git diff | Mostra as diferenças do arquivo que não foram preparadas |
```

Resultado: 

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/tabela2_result.png
)


Você ainda pode alinhar o texto à esquerda, direita ou no centro. Usando o ```:```. Assim como: 

- Alinhado a esquerda: usar ```:``` no lado esquerdo (alinhamento padrão);

- Alinhado a direita: usar ```:``` no lado direito;

- Centralizado: usar ```:``` dos dois lados.
```
|   Esquerda   |  Centralizado  |    Direita    |
| :---         |     :---:      |          ---: |
| x1           | x3             | x5            |
| x2           | x4             | x6            |
```
Resultado: 

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/tabela3_result.png
)
            
### 9. Trechos de código

Há dois modos de adicionar trechos de código ao Markdown:

* Código em linha (inline): adicione um acento grave ```ˋ``` no início e no final do código.

* Múltiplas linhas de código: envolva as linhas de código com três acentos graves ```ˋˋˋ``` ou três tils ```~~~```.

~~~
Esta é uma linha que contém um `código`.
```
Esta é uma linha de código
```
~~~

Resultado:

![](https://github.com/Ewertonslv/Tutoria/blob/main/Markdown/imagens/codigo_result.png
)

## Para saber mais
--- 
[Documentação oficial Markdown](https://daringfireball.net/projects/markdown/) 

[Como o GitHub usa Markdown](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github)

[Markdown and Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown)

## Exercícios
---
1. Deveremos propor aqui algum exercicio para a validação da metodologia usada na Tutoria, que tem como proposta DIY ( Do It Yourself ), onde o aluno deverá seguir os passos e no final ele tenha que usar o que foi ensinado para validar o ensino.
