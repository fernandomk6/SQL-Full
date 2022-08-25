# Projeções

- Seleção

  Básicamente é o que o `FROM` faz.

  Está relacionado ao FROM, de onde os dados da projeção (SELECT) serão
  buscados.

- Projeção

  Básicamente é o que o `SELECT` faz.

  É o que se projeta na tela. É o que você quer ver. SELECT lida com os
  dados que serão projetados. Tudo que vem depois do select é a projeção,
  ou seja, os dados que serão vistos na tela.

- Junção

  Básicoamento os `JOINs`.
  
  Uni o erganiza os dados selecionados pela seleção e organiza na projeção.

O SELECT faz parte da projeção

## SELECT

`SELECT NOW() AS 'Data', 'Fernando' AS 'Meu nome';`

Perceba que nesse exemplo não trouxemos dados de nenhuma tabela e sim
construímos uma tabela. Fizemos uma projeção. O select é uma projeção e 
isso vai além de trazer dados de uma tabela.

`SELECT c.nome AS 'Cliente' FROM cliente c;`

```
+----------+
| Cliente  |
+----------+
| Fernando |
+----------+
```

Perceba que o que vem a direita do operador `AS` vem o título da coluna,
o que vem a esquerda é o dado que será mostrado na coluna.

## Dicas

Evite usar `SELECT *` pois esse custa muito recurso, use apenas se o cliente precisar
de todos os dados mesmo. Do contrário selecione apenas os campos necessáarios para
evitar desperdício de tempo e de processamento.

O `SELECT *` também **ignora** os índices, logo aumenta o processamento e tempo de resposta,
então, evite usar `SELECT *`, mesmo que queira todos os dados.