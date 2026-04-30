# Tradutor Técnico

Responsável por transformar o pedido do cliente em decisões técnicas.

---

## Cadeia de relacionamentos

```
users.id → posts.userId → comments.postId
```

- Um usuário pode ter vários posts
- Um post pode ter vários comentários
- Os comentários pertencem a um post específico

---

## Tabela de rotas

| Ação do cliente | Método |        Rota             |                 O que a rota faz                         |
|-----------------|--------|-------------------------|----------------------------------------------------------|
| Listar todos os |  GET   |https://jsonplaceholder. |Retorna um array com 10 usuários. Cada objeto             |
|usuários na tela |        |typicode.com/users       |contém `id`, `name`, `username`, `email`, `address`,      |
|inicial          |        |                         |`phone`, `website` e `company`. O painel usa `name`,      |
|                 |        |                         |`username`, `email`, `address.city` e `company.name` na   |
|                 |        |                         |listagem inicial.                                         |
|-----------------|--------|-------------------------|----------------------------------------------------------|
| Clicar em um    |  GET   |https://jsonplaceholder. |Filtra os posts pelo `userId` do usuário selecionado.     |
|usuário e ver    |        |typicode.com/posts?      |Retorna até 10 posts, cada um com `id`, `userId`,         |
|seus posts       |        |userId={id}              |`title` e `body`. O painel exibe o `title` e um trecho    |
|                 |        |                         |do `body`. A ligação é `users.id = posts.userId`.         |
|-----------------|--------|-------------------------|----------------------------------------------------------|
| Clicar em um    |  GET   |https://jsonplaceholder. |Retorna os comentários vinculados ao post pelo `postId`.  |
|post e ver seus  |        |typicode.com/posts/      |Cada comentário tem `id`, `postId`, `name`, `email` e     |
|comentários      |        |{id}/comments            |`body`. O painel exibe o `name` e o `body`. A ligação     |
|                 |        |                         |é `posts.id = comments.postId`.                           |
|-----------------|--------|-------------------------|----------------------------------------------------------|

---

## Campos úteis por endpoint

### `/users`

| Campo         | Tipo        | Uso no painel                         |
|---------------|-------------|---------------------------------------|
| `id`          | number      | Chave para buscar os posts do usuário |
| `name`        | string      | Exibido na listagem                   |
| `username`    | string      | Exibido na listagem                   |
| `email`       | string      | Exibido na listagem                   |
| `address.city`| string      | Exibido na listagem                   |
| `company.name`| string      | Exibido na listagem                   |
| `phone`       | string      | Tela de detalhes                      |
| `website`     | string      | Tela de detalhes                      |

### `/posts?userId={id}`

| Campo         | Tipo        | Uso no painel                                    |
|---------------|-------------|--------------------------------------------------|
| `id`          | number      | Chave para buscar os comentários do post         |
| `userId`      | number      | Liga o post ao usuário (`users.id = posts.userId`) |
| `title`       | string      | Exibido na listagem de posts                     |
| `body`        | string      | Exibido como trecho na listagem                  |

### `/posts/{id}/comments`

| Campo         | Tipo        | Uso no painel                                            |
|---------------|-------------|----------------------------------------------------------|
| `postId`      | number      | Liga o comentário ao post (`posts.id = comments.postId`) |
| `id`          | number      | Identificador do comentário                              |
| `name`        | string      | Nome de quem comentou, exibido na tela                   |
| `email`       | string      | Email do comentador                                      |
| `body`        | string      | Texto completo do comentário, exibido na tela            |

---

## Tratamento de erro

Todos os erros de fetch devem ser capturados com `try/catch`. Nenhuma mensagem técnica deve aparecer na tela. Exemplos de mensagens amigáveis:

- "Não foi possível carregar os dados agora. Tente novamente depois de alguns minutos."
- "Ocorreu um problema ao buscar os posts deste usuário."
- "Não foi possível carregar os comentários deste post."
