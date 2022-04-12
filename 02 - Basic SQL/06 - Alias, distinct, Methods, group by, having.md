# Alias

*Aliases* são como apelidos, um nome temporário para uma tabela ou uma coluna, com o objetivo de facilitar a escrita de certos pedidos. Podemos usar *aliases* com colunas,
tabelas, e funções do *MySQL*.

~~~MySQL
SELECT NomeDaColuna AS NomeTemporário
FROM NomeDaTabela;
~~~

(***Aqui o curso cita diversos exemplos interessantes e vale ressaltar alguns deles.***)

Usando o *aliases* com funções do *MySQL*, junto do *order by*, com ele o código fica mais enxuto e fácil de compreender.

Exemplo sem alias:

~~~MySQL
SELECT CONCAT(FirstName,' ', SecondName)
FROM Actors
ORDER BY CONCAT(FirstName,' ', SecondName);
~~~

Exemplo com alias:

~~~MySQL
SELECT CONCAT(FirstName,' ', SecondName) AS FullName 
FROM Actors 
ORDER BY FullName;
~~~

Ambos mostrarão o mesmo resultado, entretanto um possuí melhores práticas.

Alguns *aliases* são inevitáveis. Para instâncias nós podemos usar alias duas vezes na mesma tabela, para comparar valores, e resgatar apenas uma que satisfaçam certas condições.

Exemplo:

~~~MySql
SELECT t1.FirstName, t1.NetworthInMillions
FROM Actors AS t1,
Actors AS t2
WHERE t1.NetworthInMillions = t2.NetworthInMillions
AND t1.Id != t2.Id;
~~~

Percebe-se que a resposta será os atores que possuem a mesma NetWorth.

## **Distinct**

Esse parâmetro tem como objetivo remover respostas iguais.

~~~MySQL
SELECT DISTINCT col1
FROM table;
~~~

Como por exemplo, se uma coluna possui apenas 3 entradas possíveis, o retorno usando o *DISTINCT* será apenas essas 3 entradas.

## **Aggregate Methods**

Demonstraremos nessa parte algumas funções built-in do *MySQL*, as quais facilitam diversos processos.

Exemplo:

~~~MySQL
SELECT FUNÇÃO(NomeDaColuna)
FROM NomeDaTabela;
~~~

### **COUNT(NomeDaColuna)**

Essa função conta o número de linhas em uma certa coluna.

~~~MySQL
SELECT COUNT(*) 
FROM NomeDaTabela;
~~~

### **SUM(NomeDaColuna)**

Essa função soma todos os valores da coluna. (*Quando os dados não são compatíveis com a soma, string por exemplo, retorna 0.*)

~~~MySQL
SELECT SUM(NomeDaColuna) 
FROM NomeDaTabela;
~~~

### **AVG(NomeDaColuna)**

Essa função retorna o valor médio da coluna. (*Também acaba retornado 0, se posto em string.*)

~~~MySQL
SELECT AVG(NomeDaColuna) 
FROM NomeDaTabela;
~~~

### **MAX(NomeDaColuna) / MIN(NomeDaColuna)**

Essas funções retornam, respectivamente, o maior e o menor valor da coluna. (*Essa é compatível ao menos com strings, ele considerará a ordem alfabética.*)

~~~MySQL
SELECT MAX(NomeDaColuna) FROM NomeDaTabela;

SELECT MIN(NomeDaColuna) FROM NomeDaTabela;
~~~

Essas são apenas poucos exemplos comparados as possibilidades oferecidas.

## **Parâmetro GROUP BY**

O *GROUP BY*, como o nome sugere, organiza linhas em grupos que são definidos pelos valores da certa coluna que escolhermos, linhas com o mesmo valor nessa coluna serão agrupadas. Muitas vezes esse parâmetro é usado junto com as funções do *MySQL*, tendo em vista que ele nos permite ver diversos tipos de dados.

Sintaxe exemplo:

(*Esta foi a sintaxe que eu pensei que pode melhor representar, mas sei que existem diversas possibilidades nas escolhas das colunas, e o curso apresenta algumas possibilidades e utilidades.*)

~~~MySQL
SELECT NomeDaColuna1, FUNÇÃO(NomeDaColunaN)
FROM NomeDaTabela
GROUP BY NomeDaColuna1;
~~~

## **Parâmetro HAVING**

Ficamos familiar com o parâmetro *WHERE* que é usado para filtrar as linhas. Da mesma forma o HAVING nos permite filtrar grupos. Esse parâmetro deve ser usado para decidir quais linhas formam cada grupo. Exatamente como o *WHERE*, mas com essa diferença. (*Ele explica que o HAVING pode ser usado para filtrar linhas, mas que é o WHERE é mais eficiente.*)

~~~MySQL
SELECT NomeDaColuna1, função(NomeDaColunaN) AS count
FROM NomeDaTabela
GROUP BY Colunas
HAVING count > 75;
~~~
