# Tipos de dados

## Caracteres literais

- CHAR
- VARCHAR

## Caracteres númericos

- INT: números sem virgulas, números inteiros. O maior tamanho é de 11 digitos.
- FLOAT: números com vírgulas. em SQL usamos `FLOAT(<quantidade total de digitos>, <quantidade de casas decimais>)`. Ou seja
se queremos armazenar 1050,20 usamos `FLOAT(6, 2)`.

*Usamos campos númericos geralmente quando precisaremos fazer operações matemáticas*.

## Fotos e documentos

- BLOB

## Textos extensões

- TEXT

# Observações

- Cada caracteres em um campo, ocupa 1 byte. Ex: "João" possuí 4 bytes.
- Um select em um banco de dados funciona como um download na internet. Quantos mais
bytes forem resgatados do banco, maior será o tempo de execução da consulta.
- Tipar o banco de dados de forma não otimizada fará com que uma consulta, traga
mais dados do que é realmente necessário, logo isso fará com que a consulta demore mais
para ser realizada.
- CHAR vs VARCHAR: A principal diferença é que o CHAR, não varia de tamanho, ou seja:
CHAR(4), ocupará 4 bytes (1 byte para cada caractere). VARCHAR(4) ocupará apenas o que
for preenchido no campo, ou seja, um campo VARCHAR(10) com a string "Fernando", ocupará
apenas 8 bytes. A mesma string se informada em um campo CHAR(10) ocuparia 10 bytes.
O CHAR tem seu tamanho fixo. Ao definir CHAR(50) o tabalho é setado nesse momento.
O VARCHAR apenas seta um tamanho limite, mas pode ocupar menos dependendo da necessidade.
**Importante** o CHAR é ligeiramente performático, pois não fica alterando de valor.
Então para falores que não variam nunca é mais performático usar o CHAR ao invés do VARCHAR.
Use VARCHAR para campos que terão tamanhos diferentes, se seu campo tiver sempre o mesmo tamanho,
use o CHAR.