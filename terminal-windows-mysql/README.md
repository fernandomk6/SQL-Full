# Terminal windows mysql

## Acessando o banco de dados

Lembre-se o mysql é um sgdb ou seja, possí diversos bancos, antes de entrar em um
banco, é necessário conectar-se ao mysql.

### Conectando-se ao mysql

Para se conectar ao mysql acesse pelo terminal a pasta onde está instalado o 
mysql. Caso use o xampp ou wampp, a pasta é c://xampp/mysql/bin. Caso tenha
o mysql instalado diretamente a pasta padrão é c://myqsl.

Dentro da pasta que tem o mysql instalado execute: `mysql -u <username> -p <password>` 
para conectar ao mysql. Depois para logar no banco de dados basta executar o comando:
`USE <database>`.

## Verificando quais tabelas do banco de dados

`SHOW TABLES`.

## Verificando a estrutura das tabelas

`DESC <table>`

## Verificando bancos de dados criados

`SHOW DATABASES`