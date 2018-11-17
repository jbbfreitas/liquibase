# Liquibase

O Liquibase é uma ferramenta de gerenciamento de versões em banco de dados. 

Ela permite que ao invés de escrever código SQL diretamente no banco de dados para criar, atualizar ou descartar objetos, 
os desenvolvedores podem definir as alterações desejadas no banco através de arquivos XML.

Qualquer alteração no banco de dados é agrupada em "ChangeSet".

::: :+1: Boa Prática :::

**Como boa prática use um `ChangeSet` para cada modificação no banco,
permitindo assim poder fazer um `rollback`, para uma versão anterior, facilmente.**
         



Alterações no banco de dados podem ser gerenciadas. Por exemplo, você pode marcar sua estrutura de banco de dados como um 
versão 1.0 (criando uma tag) após a primeira execução. 
Posteriormente, quando algumas correções forem feitas e a versão for atualizada para 1.1, 
você pode criar uma tag para  essas alterações feitas até o momento denominando-a, por exemplo de 1.1. 

Com a ajuda dessas tags, você pode reverter a estrutura do banco de dados de volta para uma determinada versão. 

::: :pushpin: Importante :::

> O liquibase gerencia versões das estruturas de um banco de dados, por exemplo
a criação de um novo índice ou a alteração do nome de uma coluna. O liquibase **não gerencia versões dos conteúdos** (dados) do banco.

## Conceitos Básicos

### ChangeSet 
> Ou  conjunto de mudanças é um agrupamento lógico de alterações no banco de dados. 
Por exemplo, um conjunto de mudanças pode ter operações para criar uma tabela, 
renomear uma coluna, adicionar uma chave estrangeira ou qualquer outra operação do banco de dados.

Como é que o liquibase identifica um ChangeSet? 
O changeset é identificado através de 3 elementos: id + autor + nome do arquivo de log de alterações (com caminho). 
Quando executar o liquibase pela primeira vez, ele irá criar 2 tabelas extras no seu banco de dados, 
`databasechangelog` e `databasechangeloglock`.


![GitHub Logo](changeLog_img.png)
Format: ![Alt Text](url)



