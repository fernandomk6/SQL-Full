# anotações gerais a respeito do curso

Um banco de dados é uma serie de arquivos que vão se alterando conforme o banco de dados
é manipulado.

## Escopo de projeto

É a definição de onde começa e onde termina o projeto, ou seja o que engloba o projeto.

## Fases da modelagem de dados

- Modelagem conceitual
- Modelagem lógica
- Modelagem física

### Modelagem conceitual

É um rascunho, não possui regra definida. Seu objetivo é iniciar a visualização 
prática do banco de dados e suas regras mais básicas, sem se preocupar com
regras de estruturação. Pode ser feito em qualquer ambiente inclusive uma folha 
de papel.

### Modelagem lógica

É a estruturação dos dados e das regras feitas na modelagem conceitual. Geralmente
usamos um software para criar um diagrama ER, que nada mais é do que uma representação
visual das estruturas de dados e dos relacionamentos de forma mais clara. Prepara
tudo para a modelagem física que é a próxima etapa.

### Modelagem física

É a estruturação dos scripts com base no SGDB escolhido com a finalidade de criar
efetivamente o banco de dados.

## Ecosistema do banco de dados

- Um SGDB pode ter varios bancos
- Um banco pode ter varias entidades
- Um entidade pode ter varios atributos
- Um atributo possui um tipo de dado

