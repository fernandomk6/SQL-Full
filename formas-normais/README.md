# Formas normais

## Primeira forma normal

- Todo campo vetorizado se tornará outra tabela

  Vetorizado significa uma lista (array), com mais de um valor, que 
  são da mesma família.

- Todo campo multivalorado se tornará outra tabela

  Multivalorado significa que o campo pode ser divisível.
  Divisível é um campo que é como um vetor, porém não pertencem a
  mesma família.

- Toda tabela precisa de um campo que identifique todo o registro
como sendo único.

  Toda tabela precisa de um ID (identificação).
  Essa identificação caracteriza-se pela chave primaria (primary key).
  A primary key existe para criar uma identificação daquele registro e
  ele deve ser único.

  - Cardinalidade 

  As cardinalidades podem ser
  (0,1), (0,n), (1,1), (1,n)

  O primeiro define a obrigatoriedade. 1 = sim, 0 = não.
  O segundo define a quantidade maxima. 1 = no máximo 1, n = vários.

  TELEFONE(0, n) < RELAÇÂO > (1, 1)CLIENTE(1, 1) < RELAÇÂO > ENDEREÇO(1,1)

  Simplificando

  Primeiro tratamos a relação entre TELEFONE para CLIENTES.
  O telefone é obrigatório no cadsatro de clientes? não. Então o primeiro
  número da cardinalidade de telefone, será 0. Obrigatório = não.
  Qual o numero máximo de telefone que o cadastro de clientes pode ter?
  Mais de um. Então o segundo digitto da cardinalidade será n. Então
  teremos TELEFONE(0, n).

  Agora precisamos colocar a cardinalidade da entidade clientes.
  O cliente é obrigatorio no cadastro do telefone? sim. Então teremos 
  o primeiro digito como 1.
  Qual o número máximo de clientes que o cadastro de telefone pode ter? 1.
  Ou seja, o segundo digíto também será 1. Então teremos (1, 1)CLIENTE.

  TELEFONE(0, n) < RELAÇÃO > (1, 1)CLIENTE.

  Apara dizermos a relação falamos um para n. Para isso consideramos apenas o
  segundo digito das relações TELEFONE(n) CLIENTES(1). Então podemos dizer
  que a relação de clientes para telefone é de 1 para n. E que a relação
  de telefone para clientes é de n para 1.

## Chave estrangeira (foreign key) 

A chave estrangeira é uma chave, que referencia uma chave primaria de outra
tabela.

A foreign key depende da cardinalidade.

### Regras FK e cardinalidade

- Em cardinalidade 1x1 a chave estrangeira vai na tabela mais fraca.
- Em cardinalidade 1xn a chave estrangeira ficará sempre na tabela que tiver
a cardinalidade n.

Relacionamento 1x1 na foreign key da tabela mais fraca, no modelo físico, devemos 
utilizar o `UNIQUE`, para asegurar que não haverá registro duplicados.

```SQL
CREATE TABLE endereco (
  id INT PRIMARY KEY AUTO_INCREMENT,
  -- Campos da tabela
  id_cliente INT UNIQUE,

  FOREIGN KEY (id_cliente) REFERENCES cliente(id)
);
```

Perceba que no campo id_cliente usamos o `UNIQUE`, para dizer que não pode 
existir 2 endereços com o mesmo cliente.

**Em relacionamento 1xN, não usamos o `UNIQUE`**
