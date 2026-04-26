# Endpoint `/posts`

## Retorno
O endpoint retorna uma lista de posts.

## Link usado
`https://jsonplaceholder.typicode.com/posts/?userId=1`

## Campos de cada post
- `userId` → number
- `id` → number
- `title` → string
- `body` → string

## Como `userId` conecta o post ao usuário?
A relação é:

`users.id = posts.userId`

todos os posts retornados têm `userId = 1`, então pertencem ao usuário de `id = 1`.

## Quantos posts retornam?
No retorno enviado, retornam **10 posts**.

## Campos mais úteis para o painel
Para exibição na interface:

- `title`
- trecho do `body`
- `id` do post
