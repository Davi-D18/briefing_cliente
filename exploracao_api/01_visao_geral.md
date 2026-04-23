## Relação principal entre os dados
A estrutura geral é:

`users.id -> posts.userId -> comments.postId`

Isso significa que:

- um usuário pode ter vários posts
- um post pode ter vários comentários
- os comentários pertencem a um post específico

## Visão do painel
O painel simples pode seguir este fluxo:

1. listar usuários
2. clicar em um usuário e ver seus posts
3. clicar em um post e ver seus comentários
