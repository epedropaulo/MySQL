# Inserindo Data

Aprenderemos a como inserir data usando o *INSERT*.

~~~MySQL
INSERT INTO NomeDaTabela 
(NomeDaColuna1, Col2, ..., Coln)
VALUES (ValorDaColuna1, Val2, ..., valn);
~~~

Não precisamos listar o nome da coluna em ordem que foi posto para criar a tabela, apenas é necessário que os valores correspondam com a coluna certa na mesma ordem.

Nós também podemos adicionar diversas linhas ao mesmo tempo usando o *INSERT*. A sintaxe nos pede para separá-los usando vírgula.

~~~MySQL
INSERT INTO NomeDaTabela (OrdemDasColunas)
VALUES (OrdemDosValores1), (OrdemDosValores2);
~~~

Esse método de inserir linhas é um jeito mais rápido do que inserir uma a uma. Adicionar múltiplas linhas da oportunidade ao MySQL de otimizar os inserts.

Entretanto, podemos usar também uma sintaxe diferente que não precisamos, citar o nome das colunas. Porém, é necessário colocar os valores na ordem padrão que a tabela foi organizada.

~~~MySQL
INSERT INTO NomeDaTabela
VALUES (valor1, valor2, valor3, valor4);
~~~

E ainda há uma terceira forma de adicionar linhas a nossa tabela, que é usando o nome da coluna e o valor logo em seguida. Essa sintaxe alternativa faz uso do *SET*.

~~~MySQL
INSERT INTO NomeDaTabela SET NomeDaColuna=Valor, ... ;
~~~

## **Mostrando data**

Aprenderemos a como pedir a data, de tabelas, usando o *SELECT*.

~~~MySQL
SELECT NomeDaColuna, Col2, ..., Coln
FROM NomeDaTabela
WHERE Condições;
~~~

O comando *SELECT* é seguido das colunas que queremos exibir. Usando * mostramos todas as colunas, e são mostradas na ordem que aparecem no MySQL.

Nós também podemos fazer com que apenas linhas sob certas condições apareçam, como por exemplo números acima de 5, ou apenas pessoas que começam com a letra
f.

Entretanto, para fazer o exemplo dos nomes que começam com F, precisaremos do operador *LIKE*, que é uma adição ao *WHERE*, exemplo:

~~~MySQL
SELECT * FROM Actors WHERE FirstName LIKE "Jen%";
~~~

A resposta será todos os dados das pessoas que o "FirstName" começam com "Jen".

O operador *LIKE* funciona apenas para data do tipo string, e nos permite achar linhas baseado no padrão que selecionarmos. Pode se fazer isso também para o comando *SHOW*.
