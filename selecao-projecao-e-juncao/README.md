# Selecão, projeção e junção

Uma query usa seleção projeção e junção

**Seleção não é o select**.

## Projeção

É tudo que você quer ver na tela (colunas).
Em uma query começe com as projeções.

```sql
SELECT nome, email, telefone
```

## Seleção

**Banco de dados relacional é teoria dos conjuntos**.

Seleção é um subconjunto do conjunto total de registros de uma tabela.
**A cláusula de seleção é o where**.

Conjunto de clientes: cliente1, cliente2, cliente3 etc.
No conjunto de clientes exitem homens e mulheres.
Teríamos um subconjunto de homens clientes.

**O conjunto total é uma tabela**

```sql
SELECT nome, telefone -- Projeção.
FROM clientes -- Origem.
WHERE sexo = 'f'; -- Seleção.
```

## Junção

Exemplo

*Não usem assim pois where é seleção e não junção*

```sql
SELECT nome, email, bairro, rua
FROM clientes, enderecos
WhERE clientes.primary_key = enderecos.foreign_key;
```

Para junção usamos a cláusula **JOIN**

```sql
SELECT nome, email bairro, rua
FROM clientes
INNER JOIN enderecos
ON clientes.id = enderecos.cliente_id;
```

Filtrando (selecionando)

```sql
SELECT nome, email bairro, rua -- Projeção.
FROM clientes -- Origem.
INNER JOIN enderecos -- Junção.
ON clientes.id = enderecos.cliente_id; -- Condição da junção.
WHERE sexo = 'f'; -- Seleção.
```

### Junção com 3 tabelas

Busque os dados, nome, email, bairro, cidade, telefone

```sql
SELECT nome, email, bairro, telefone
FROM clientes
    INNER JOIN enderecos
    ON clientes.id = enderecos.cliente_id
    INNER JOIN telefones
    ON cliente.id = telefones.cliente_id
```