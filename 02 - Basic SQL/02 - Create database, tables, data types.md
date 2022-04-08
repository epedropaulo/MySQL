# Criando databases

Uma **database** é um container que armazena todas as suas tabelas. Uma tabela armazena a data organizada em linhas e colunas. Uma coluna
é um pedaço de data que é um dos atributo de uma entidade. Uma linha é um conjunto de colunas que definem os atributos dessa entidade.

Comando | Função
:------: | :------:
Create database NomeDaDatabase; | Cria uma database completamente nova.
Drop database NomeDaDatabase; | Deleta uma database.

(*É possível também em SQL, usar comandos para executar apenas sob certas circunstâncias, um exemplo disso é o comando a seguir:*)

~~~MySQL
CREATE DATABASE IF NOT EXISTS NomeDaTabela;
~~~

## **Tipos de dados**

Antes de começarmos a criar tabelas, examinaremos os conceitos de uma tabela.

As colunas necessitam da definição do tipo de data que ela carregará, é isso que faz a tabela ser estruturada. E a maioria da categoria de data são:

- **Numéricos**: Int, BigInt, TinyInt, Decimal, etc.
- **Data e hora**: Date, Time, TimeStamp, Year, etc.
- **String**: Varchar, Char, Enum, Set, Blob, etc.
- **Spatial Data**: Representa localização, tamanho e formato de um objeto no planeta Terra, como construções, lagos, montanhas e cidades.

## **Criando tabelas**

Quando criamos tabelas, precisamos especificar seu nome, colunas e que tipo de data cada coluna suporta, e ainda existem outras coisas que podemos especificar, essa parte entraremos em mais detalhes depois.

~~~MySQL
CREATE TABLE NomeDaTabela(
    NomeCol1 TipoDeData <Restrições>,
    NomeCol2 TipoDeData <Restrições>,
    NomeCol3 TipoDeData <Restrições>
)
~~~

## **Restrições**

1. Em uma database relacional nós devemos identificar uma linha, escolhendo uma coluna ou um conjunto de colunas como a chave primária. Uma forma muito comum de identificarmos apenas uma linha é adicionarmos uma coluna ID, que recebe um numérico diferente para cada linha da tabela, e para isso o *MySQL* tem uma função muito interessante, chamada *AUTO_INCREMENT* que por default põe o próximo número inteiro.

2. Restringir as possibilidades de entrada, como por
exemplo, impedir que seja posto como data o 'null', conhecido como vazio. E para isso podemos marcar a coluna como: not null, assim o usuário é obrigado a passar um valor valido para a coluna.

3. Também podemos usar um valor DEFAULT, para caso um parâmetro não seja passado, será definido um valor padrão, para melhor análise posterior da data.

Lembrando que podemos aplicar essas restrições em conjunto, para criar uma database que possua a data bem organizada e específica.

### **Tabelas temporárias**

Existem também tabelas do tipo temporária, que é igual a uma tabela padrão. Entretanto quando a interface do MySQL for finalizada essa tabela se apagará.

~~~MySQL
CREATE TEMPORARY TABLE NomeDaTabela(
    Colunas, TipoDeData, <restrições>
)
~~~
