# Endpoint `/comments`

## Retorno
O endpoint retorna uma lista de comentários de um post.

## Link usado
`https://jsonplaceholder.typicode.com/posts/1/comments`

## Campos de cada comentário
- `postId` → number
- `id` → number
- `name` → string
- `email` → string
- `body` → string

## Como o comentário se vincula ao post?
A relação é:

`posts.id = comments.postId`

No exemplo analisado, todos os comentários têm `postId = 1`, então pertencem ao post de `id = 1`.

## Quantos comentários retornam?
Retornam **5 comentários**.

## Campos mais úteis para o painel
Para exibir comentários na interface:

- `name`
- `body`
