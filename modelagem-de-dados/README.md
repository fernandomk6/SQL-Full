# Modelagem de dados

[Referência](https://www.devmedia.com.br/tecnologias-de-banco-de-dados-e-modelagem-de-dados/1660https://www.devmedia.com.br/tecnologias-de-banco-de-dados-e-modelagem-de-dados/1660)

Um banco de dados é um conjunto de dados que possui um significado e objetiva
atender um ou mais usuários. Por exemplo, um catálogo telefônico pode ser
considerado um banco de dados. Sendo assim, bancos de dados não necessáriamente
são eletrônicos ou informativados.

Quando resolvemos informativar um banco de dados usamos um software SGDB que significa
sistema gerenciador de banco de dados. Exemplos de SGBs: firebird, mySql, SQL server entre outros.

Em um SGDB relacional os conjuntos de dados são armazenados em tabelas.

## Etapas da modelagem

Quando precisamos solucionar um problema com programação, geralmente pensamos em três
etapas:

- Entendimento do problema
- Construção do algoritmo
- Implementação na linguagem de programação escolhida

Se tratando de  banco de dados não é muito diferente:

- Entendimento do problema
- Construção do modelo ER – entidade e relacionamento
- Implementação no SGBD escolhido

Entendimento do problema

Nem sempre é fácil entender um problema. O profissional deve saber ouvir bem o cliente e saber
abstrair os problemas reais do cliente para o software de forma lógica.

Antes de implementar o banco de dados usando um SGDB é necessário descrever o banco de dados
de forma independente. Essa etapa é chamada de modelo conceitual.

Costumamos representar esse modelo conceitual usando um diagrama ER (entidade-relacionamento).

![entidade-relacionamento](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/17-04pic2.JPG)

## Modelo ER

- Entidade

Entidade pode ser entido como algo da realidade modelada em forma de propriedades e valores. Por exemplo
em uma escola, temos as entidades alunos, professores. Alunoes possuem propriedades como nome, turma e 
professores possuem, nome, disciplina etc. Vale ressaltar que entidade pode ser coisas reais como pessoas,
ou coisas abstratas, como horários.

A entidade é representada por um retângulo, que contém o nome da entidade. Observe o exemplo abaixo.

![Exemplo de entidade](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic01.JPG)

- Relacionamento

Relacionamento é um conjunto de associações que unine duas ou mais entidades.

O relacionamento é representado por um losango. Esse losango é ligado por linhas aos retângulos 
que representam as entidades participantes do relacionamento. O exemplo abaixo possui duas 
entidades, MÉDICO e PACIENTE, e um relacionamento chamado CONSULTA.

![Relacionamento consulta](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic02.JPG)

Um relacionamento pode envolver ocorrências de uma mesma entidade. Neste caso, 
estamos diante de um auto-relacionamento. Observe o exemplo:

![Relacionamento casamento](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic03.JPG)

Observe o modelo abaixo:

![Relacionamento possui](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic04.JPG)

Estamos diante de um relacionamento (possui) entre as entidades EMPREGADO e DEPENDENTE. 

Considere as seguintes questões:

- Um empregado pode não ter dependentes?
- Um dependente pode ter mais de um empregado associado ?
- Determinado empregado pode possuir mais de um dependente?
- Pode existir dependente sem algum empregado associado?

Na realidade, as respostas desses questionamentos dependem do problema sendo modelado. 
Entretanto, para que possamos expressar essas idéias no modelo, é necessário definir uma 
propriedade importante do relacionamento: **sua cardinalidade**.

Cardinalidade é um numero que expressa com quantas entidades um relacionamento pode está associado. 
Se uma entidade pode se relacionar com apenas um outra unidade, ou com várias outras ou com nenhuma.

Obeserve o exemplo abaixo:

![Cardinalidade](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic05.JPG)

A cardinalidade de uma entidade é representada do lado oposto. Desse exemplo podemos entender que
A entidade Empregado possuí a cardinalidade (0, n) em relação ao dependente. Podemos entender
então que um empregado pode ter no mínimo 0 dependentes e no máximo n (indeterminados).
Já a entidade dependente que possuí a cardinalidade (1, 1) pode se relacionar com no mínimo 1
empregado e no máximo 1.

A cardinalidade é expressada no final do relacionamento, entre parênteses. O primeiro número 
é a ocorrencia mínima e o segundo é a ocorrência máxima. Ocorrência máxima "n" significa, um
número ilimitado de ocorrencias. A cardinalidade (1, n) pode ser lida como "um para muitos",
e significa que a entidade em questão pode se relacionar com muitas outras entidades.

Geralmente para cardinalidades mínimas usamos 0 para nenhum ou 1 para apenas 1.
E para máximas usamos 1, ou n para mais de 1.

- Atributos

Atributos são os campos de cada entidade. Por exemplo entidade alunos possuí os attributos
nome, turma, idade.

- Cardinalidade dos atributos

![Cardinalidade dos atributos](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/18-05pic07.JPG)

Perceba que declaramos que um aluno pode ter no mínimo 0 telefones e no máximo n.

A cardinalidade de (1, 1) por padrão deve ser omitida. Ou seja as cardinalidades de nome e codigo
são (1, 1) (Ler se "um para um").

No caso de atributos:

- Cardinalidade mínima 1 indica que o atributo é obrigatório
- Cardinalidade máxima 1 indica que o atributo é monovalorado
- Cardinalidade mínima 0 indica que o mesmo é opcional
- Cardinalidade máxima N informa que ele é multivalorado

- Atributo identificador

É um atributo que tem o papel de distinguir uma ocorrência da entidade das demais 
ocorrências da mesma entidade.

- Generalização / ESpecialização

Consiste em abstrair atributos comuns a entidades em uma nova entidades e apenas usar um identificador
para cada ocorrencia da entidade.

![Generalização / ESpecialização](https://www.devmedia.com.br/imagens/sqlmagazine/abr2006/19-06pic12.JPG)

Existem dois tipos de generalização / especialização

As denominadas P (parciais) e T (totais)

As totais querem dizer que para cada ocorrencia da entidade base, deve existir uma ocorrencia da entidade 
especializada.

As parciais dizem que para cada ocorrência da entidade base, pode ou não ter uma ocorrencia da 
entidade especializada.

- Entidade associativa.

O modelo de entidades e relacionamentos não permite um relacionamento entre relacionamentos.
Mas em alguns casos isso é necessário. Quando isso é necessário tornemos uma entidade como 
ocorreência de um relacionamento. Representamos de forma gráfica através de um retangulo envolta do
relacionamento.