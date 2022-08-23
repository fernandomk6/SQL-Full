# Conceitos fundamentais

[referência](https://www.devmedia.com.br/conceitos-fundamentais-de-banco-de-dados/1649)


##  O que é um banco de dados

Banco de dados é um conjunto de dados que se relacionam.

### O que são SGDBs?

SGDBs (Sistema de gerenciamento de banco de dados) são softwares que possuem mecanimos
para manipular um banco de dados e interagir com o usuário. Exemplos de SGDBs: MySql,
PostgreSQL, SQL Server, Oracle entre outros.

Podemos conceituar um sistema de gerenciamento de banco de dados com quatro componentes
básicos: software, hardware, usuário e os dados. Sistema de banco de dados pode ser
considerado como "uma sala eletrônica de arquivos".

![Componentes de um sistema de banco de dados](https://www.devmedia.com.br/imagens/sqlmagazine/mar2006/ORA_RR_01.JPG)

O principal objetivo dos SGDBs são de abstrair a manipulação dos dados da aplicação e do usuário, tornando
assim, o banco de dados independente).

## Projetos de banco de dados

Todo bom banco de dados deve ter um projeto. Esse projeto visa tornar o banco de dados manitenível a 
longo prazo, escalavel e performático.

Um projeto de bancos de dados se dá em duas fases:

- Modelagem conceitual 
- Modelo lógico

### Modelagem conceitual

É o planejamento das estruturas de dados independente do SGDB

[Relacionamento de entidades](https://www.devmedia.com.br/imagens/sqlmagazine/mar2006/ORA_RR_03.JPG)

### Modelo lógico

Descreve a estrutura do banco de dados de acordo com o tipo de SGDB usado. 
Tipos de SGDBs: 

- Hierárquico
- Relacional
- Orientado a objetos, entre outros

O modelo mais usado é o relacional e por isso abordaremos ele aqui.
No modelo relacional, temos os dados organizados em tabelas.

O modelo lógico de um projeto usando SGDB relacional deve definir o nome das tabelas
e das colunas.

É importante salientar que, no modelo lógico não devemos nos preocupar com as particularidades do
sofware escolhido, isso acontecerá na proxima etapa: Modelo físico. Onde traduziremos o modelo
lógico para as particularidades da linguagem do software escolhido.