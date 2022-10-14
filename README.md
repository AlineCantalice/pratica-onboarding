# pratica-onboarding

## rodando a aplicação localmente

### Back-end
- npm install
- .env para o banco local
- migrar o banco
- seed

### Front-end
- npm install --force (Sem o --force não funcionou)
- usei Optional Chaining em eventInfo (context), em todos os locais que aparecia
- .env para rodar localmente

## O problema

A modelagem do banco da tabela enrollment foi feita para que aceitasse vários endereços,
até repetidos.

## Solução

- Modificar a tabela Adress para que o endereço seja destinado a tabela Enrollment com a tag @unique
- Modificar os services para fazer upsert separadamente, uma vez para a tabela enrollment pegando o id, e depois para a tabela Adress usando o id para encontrar.