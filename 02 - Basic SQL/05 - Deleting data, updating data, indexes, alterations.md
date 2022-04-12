# Alterando data

## **Deletando data**

Para deletar linhas de uma tabela, podemos usar o comando *DELETE*.

Ele deleta uma linha inteira e não colunas individuais, para mudar
uma coluna específica, precisa usar o comando *UPDATE*, o qual apresentaremos em seguida.

(*Vale ressaltar que deletar todas as linhas de uma tabela, não apaga a tabela em si.*)

~~~MySQL
DELETE FROM NomeDaTabela
WHERE CondiçãoParaTal
ORDER BY col1
LIMIT 5;
~~~

Percebe-se que assim como a maioria dos comandos o *DELETE*, também pode receber diversos parâmetros e condições.

Se nós pretendemos deletar todas as linhas de uma tabela, a maneira mais rápida é usando o comando *TRUNCATE*. Esse comando apaga a tabela inteira e a recria. Isso aumenta a velocidade de processamento.

~~~MySQL
TRUNCATE NomeDaTabela;
~~~

## **Atualizando data**

Nós podemos usar o comando *UPDATE* para mudar o valor de uma coluna em uma linha ou em múltiplas linhas.

~~~MySQL
UPDATE table
SET NomeDaColuna1 = NovoValor, Col2 = Val2, …, Coln = Valn
WHERE Condições;
~~~

Assim como a maioria dos comandos o *UPDATE*, também pode receber diversos parâmetros e condições. Se não for estabelecida uma condição, o comando modificará todas as linhas.

Ele possui duas fases. Primeiro ele descobre quais linhas satisfazem a condição e depois as modifica.

## **Chave primária e índices**

Toda vez que um comando possui o parâmetro *WHERE*, o *MySQL* tem que fazer um scan de toda a tabela para achar as linhas que o satisfazem. Isso não é muito eficiente. Adicionar um index na tabela pode aumentar significadamente a velocidade de procura pelas linhas desejadas.

O propósito do index primário é para representar a ordem
da data. a coluna que for o index primário da tabela, não pode ser nulo.

Nós podemos usar o seguinte comando para poder aparecer os índices de uma tabela:

~~~MySQL
SHOW INDEX FROM NomeDaTabela
~~~

(*Aqui o curso entra em uma grande explicação de índices agrupados e não agrupados. Mas que não descreverei por aqui.*)

Um index não vem apenas com benefícios. Primeiro, ele ocupa espaço extra no disco. Segundo, ele precisa ser modificado toda vez que adicionarmos ou atualizarmos a tabela.

## **Alterações**

Nós podemos renomear tabelas, adicionar, remover, ou renomear colunas, mudar o tipo de uma coluna existente, etc.

~~~MySQL
ALTER TABLE NomeDaTabela
CHANGE AntigoNomeDaColuna NovoNomeDaColuna <datatype> <restrictions>;
~~~

(*Nesse ponto o curso cita diversos exemplos usando a database que eles estabeleceram previamente, vale citar alguns deles.*)

No parâmetro *CHANGE*, é obrigado a mudar o nome da coluna.

~~~MySQL
ALTER TABLE NomeDaTabela CHANGE NomeAntigo NomeNovo
<Diversas alterações como tipo, default, key>;
~~~

Já no parâmetro *MODIFY* não pode mudar o nome da coluna.

~~~MySQL
ALTER TABLE NomeDaTabela CHANGE NomeDaColuna
<Diversas alterações, como tipo, default, key>;
~~~

Podemos adicionar novas tabelas, já definindo diversas características, e até em qual 'lugar' ficará essa coluna.

~~~MySQL
ALTER TABLE NomeDaTabela ADD NomeDaNovaColuna
<Características>
AFTER NomeDaColunaNaFrenteDaNova;
~~~

Também podemos apagar as colunas que desejamos.

~~~MySQL
ALTER TABLE NomeDaTabela DROP NomeDaColuna;
~~~

Pode-se renomear a tabela com *ALTER*.

~~~MySQL
ALTER TABLE NomeVelho
RENAME NomeNovo;
~~~

(*Nós também podemos colocar diversas alterações em apenas um comando, apenas os separando por vírgula.
*)

## **Alterando índices**

É complexo saber quais índices criar sem observar o padrão de acesso de uma aplicação. Nós podemos adicionar, remover ou modificar índices depois da aplicação ser posta no banco de dados. Note que modificar os índices não muda a data na tabela.

É possível adicionar e remover índices. Entretanto, precisa de um certo tipo de atenção especial, visto que se uma coluna tive auto incremento, não da pra remover sua condição
de índice primário.

~~~MySQL
ALTER TABLE NomeDaTabela ADD INDEX NomeDoÍndice NomeDaColuna ;

ALTER TABLE NomeDaTabela DROP INDEX NomeDoÍndice;
~~~
