# Outros endpoints da JSONPlaceholder

## Objetivo

Além dos endpoints usados na atividade principal, a JSONPlaceholder também possui outros recursos que servem para testes e exemplos.  
Eles não são o foco do painel pedido pelo cliente, mas ajudam a entender melhor a estrutura da API e mostram que ela oferece mais opções além de usuários, posts e comentários.

## O que a API oferece

A JSONPlaceholder vem com **6 recursos principais**:

### `/posts`
Representa publicações.  
A API possui **100 posts**.

### `/comments`
Representa comentários.  
A API possui **500 comentários**.

### `/albums`
Representa álbuns.  
A API possui **100 álbuns**.

### `/photos`
Representa fotos.  
A API possui **5000 fotos**.

### `/todos`
Representa tarefas.  
A API possui **200 tarefas**.

### `/users`
Representa usuários.  
A API possui **10 usuários**.

---

## Como esses recursos se relacionam

A API não entrega os dados totalmente separados.  
Alguns recursos estão ligados entre si.

Exemplo:

- posts podem ter comentários
- álbuns podem ter fotos

Isso mostra que a API simula uma estrutura mais parecida com um sistema real, onde uma informação pode depender de outra.

---

## Rotas que a API aceita

A JSONPlaceholder aceita vários métodos HTTP, então ela permite diferentes tipos de operação.

Os principais são:

- **GET** → buscar dados  
- **POST** → criar dados  
- **PUT** → substituir dados  
- **PATCH** → alterar parte dos dados  
- **DELETE** → excluir dados  

Exemplos de rotas mostradas na documentação:

- `GET /posts`
- `GET /posts/1`
- `GET /posts/1/comments`
- `GET /comments?postId=1`
- `POST /posts`
- `PUT /posts/1`
- `PATCH /posts/1`
- `DELETE /posts/1`

---

## O que isso significa na prática

Na prática, isso quer dizer que a API pode ser usada para estudar várias situações diferentes, mesmo sem usar dados reais.

Os outros endpoints existem na documentação e foram registrados como informação complementar, mas não fazem parte do fluxo principal pedido no desafio.
