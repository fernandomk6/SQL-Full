# JOINS

![Joins](https://arquivo.devmedia.com.br/artigos/Fernanda_sallai/sql_join/image001.jpg)

Com base na imagem acima podemos concluir que:

Existem básicamente;

- INNER JOIN / JOIN
- LEFT OUTER JOIN / LEFT JOIN
- RIGHT OUTER JOIN / RIGHT JOIN
- FULL OUTER JOIN / FULL JOIN

E temos algumas "modificações" no RIGHT e LEFT JOIN que acontecem quando
adicionamos a clausura B.key IS null (RIGHT) ou a.key IS null (LEFT).

E temos a "modificação" no FULL JOIN quando adicionamos `WHERE a.key IS null OR b.key IS null`.

Isso nos da um total de 7 JOINS

- JOIN

  Traz os registro comuns entre as duas tabelas.

- LEFT JOIN

  Traz toda a tabela LEFT e os registro comuns entre as duas.

- LEFT EXCLUDING JOIN

  Traz toda a tabela LEFT com exceção dos registros que se relacionam com a tabela RIGHT

- RIGHT JOIN

  Traz toda a tabela RIGHT e os registro comuns entre as duas.

- RIGHT EXCLUDING JOIN

  Traz toda a tabela RIGHT com exceção dos registros que se relacionam com a tabela LEFT

- FULL JOIN

  Traz todas as duas tabelas

- FULL EXCLUDING JOIN

  Traz todas as duas tabelas com exceção dos dados que estão relacionados