# Endpoint `/users`

## Retorno
O endpoint retorna uma lista de usuários.

## Link
`https://jsonplaceholder.typicode.com/users`

## Campos principais de cada usuário
- `id` → number
- `name` → string
- `username` → string
- `email` → string
- `address` → object
- `phone` → string
- `website` → string
- `company` → object

## Campos internos de `address`
- `street` → string
- `suite` → string
- `city` → string
- `zipcode` → string
- `geo` → object

## Campos internos de `geo`
- `lat` → string
- `lng` → string

## Campos internos de `company`
- `name` → string
- `catchPhrase` → string
- `bs` → string

## Quantos campos tem cada usuário?
Considerando apenas os campos principais, cada usuário tem **8 campos**.

## Campos mais úteis para o painel
Para uma tela de listagem, os mais úteis são:

- `name`
- `username`
- `email`
- `city` dentro de `address`
- `company.name`
- `phone`
- `website`

Os demais campos podem ficar para uma tela de detalhes.
