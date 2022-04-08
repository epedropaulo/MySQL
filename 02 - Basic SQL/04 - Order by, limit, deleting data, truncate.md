# Combinando condições

A syntax do *MySQL* nos permite juntar diversas condições, na hora que formos selecionar a data que desejamos ver com diversos operadores e diversos parâmetros.

Cuidado ao colocar diversos parâmetros no mesmo pedido, é preciso seguir uma certa ordem lógica.

## **Parâmetro ORDER BY**

É usado para ordenar como desejamos ver a data que pedimos, é possível colocar em ordem crescente, decrescente, colocar critérios de desempate e outros.

~~~MySQL
SELECT NomeDaColuna1, Col2, …, Coln
FROM NomeDaTabela
WHERE Col3 LIKE "%some-string%"
ORDER BY Col3;
~~~

## **Parâmetro LIMIT**

Geralmente quando estamos lidando com uma database real, podem existir milhares ou milhões de linhas, e a data pode acabar retornando linhas demais. Isso é um problema, pois pode acabar sobrecarregando o usuário que deseja ver a data e também é impraticável em um cenário posterior. O Parâmetro *LIMIT* nos permite restringir o número de de linhas que nos é
exibido de uma busca.

~~~MySQL
SELECT NomeDaColuna, Col2, …, Coln
FROM NomeDaTabela
WHERE Col3 LIKE "%some-string%"
ORDER BY Col3
LIMIT 10;
~~~

Também podemos pular algumas linhas com o parâmetro *LIMIT*, como por exemplo exibir apenas os números 4, 5, 6, 7. Pode se usar o *LIMIT* para pular os 3 primeiros. podemos colocar *LIMIT* 3,4;
