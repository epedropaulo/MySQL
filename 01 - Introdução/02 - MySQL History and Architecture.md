# Arquitetura do MySQL

O *MySQL* é composto de diversos componentes que exploraremos mais a frente. A arquitetura dele é baseada em client-server, aplicações como website ou a linha de comando do *MySQL* conecta o cliente e as database, e os fazem interagir através dos servidores *MySQL*, e o server responde aos pedidos dos clientes.

**Existem três camadas que podemos dividir o MySQL:**

1. Application/Client Layer
2. MySQL Server Layer
3. Storage Engine Layer

## **Application/Client Layer**

É a camada responsável pela conexão, autorização, autenticação e segurança do cliente.

## **MySQL Server Layer**

É a camada responsável por analisar e otimizar pedidos feitos pelos clientes. Também mantém caches e buffers.

O *MySQL* oferece built-in functionality, que também é assegurado por esta camada. Essa camada é responsável pela interface *SQL* que cuida da interação com a database, e da engine relacional. O output dessa camada é um plano de execução que é guardado na Storage engine. E ela usa para modificar ou devolver data de acordo com o plano.

## **Storage Engine Layer**

Essa camada é a parte do *DBMS* que realmente escreve, modifica e retorna a data direto do armazenamento físico.

No caso do *MySQL*, a arquitetura permite que o usuário escolha a Storage Engine de um conjunto de possibilidades. Diferentes Storage engines são feitas sob medida para certa necessidade.
