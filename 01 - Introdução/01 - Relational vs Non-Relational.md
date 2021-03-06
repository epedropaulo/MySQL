# **Relacionais vs Não Relacionais**

O curso começa com a apresentação da definição de data, a qual é definida como sendo distintos pedaços de informação. Logo nos é apresentado diferentes tipos de data.

**Data estruturada:** Possui uma certa pré-definição de organização, o que a torna mais fácil de ser analisada. A data precisa seguir um modelo padrão que diz o tamanho de cada parte da data, como: tipo, tamanho e qualquer outra restrição de valores que possa ter, e geralmente possuem um esquema formal que específica toda a estrutura da data.

O maior exemplo deste tipo são as *SQL* databases.

**Data não-estruturada:** São marcadas pela falta de uma organização e pela falta do esquema que descreve a data.

São exemplos: videos, audios, blogs, log files, social-media posts, etc. São datas sem nenhuma definição ou tipo.

**Data semi-estruturada:** É o meio termo entre os dois tipos, e também não possui, explicitamente, esquema ou modelo definido que descreva a data. Contém tags, mas não segue o padrão de estruturas associadas das típicas bases relacionais.

---
A data em si possui partes que são estruturadas e outras que não são.
A diferença real hoje entre data não-estruturada e semi-estruturada quase não existe, logo para uso didático falaremos apenas em data estruturada e não estruturada.

## **Sistema de gerenciamento de databases**

(*DBMS sigla em inglês*)

Geralmente quando nos referimos a database como o *MySQL* ou *PostgreSQL*, estamos falando de todo um sistema chamado de *DBMS*. É um software que permite o usuário, criar, fazer manutenção e deletar múltiplas ou individuais databases.

## **Databases**

Uma database é um grupo, estruturado e organizado de data, geralmente guardado de forma eletrônica. A organização e a estruturação ajudam na eficiência da análise.

Existem dois tipos de databases:

1. Relacional ou SQL databases
2. Não-relacional ou NoSQL databases

### **Relacional/SQL Databases**

Databases relacionais consiste em data armazenada como linha em tabelas. As colunas da tabela, seguem um esquema restrito que define o tipo e o tamanho de cada data que a coluna pode suportar.

A relação entre duas tabelas é definida pela coluna, ou um conjunto delas, que apareça em ambas tabelas. sistemas de gerenciamento de databases relacionais *(RDBMS)* são amplamente usados.

Uns bons exemplos são: Oracle, DB2, Microsoft SQL Server, PostgreSQL e MySQL.

### **Não-relacional/NoSQL Databases**

Como a data dada pela internet à companhias apenas aumentava, um novo método de design nas databases foi descoberto. A parte do esquema restrito foi desfavorecida, o que fez surgir uma database com esquemas menos restritos.

*NoSQL* databases podem ter diferentes formas e diferentes usos. O escopo inclui armazenamento key-value, armazenamento de colunas, armazenamento de documentos, armazenamento de gráficos e até search engines.

### **Big Data**

Big data geralmente inclui data com tamanhos além da capacidade tradicional das tecnologia *SQL*. O termo 'Big' em Big data simboliza a quantidade de data que sempre aumentará junto com a capacidade do software.
