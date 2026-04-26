# Relacionamentos e proposta de painel

## Estrutura dos relacionamentos
A API segue esta estrutura:

- **Usuário** identifica os posts
- **Post** identifica os comentários

Em forma de ligação:

- `users.id -> posts.userId`
- `posts.id -> comments.postId`

## Fluxo esperado do painel
O painel simples pode funcionar assim:

### 1. Lista de usuários
Mostrar:
- nome
- username
- email
- cidade

### 2. Posts do usuário selecionado
Ao clicar em um usuário, buscar os posts dele e mostrar:
- título
- resumo do conteúdo

### 3. Comentários do post selecionado
Ao clicar em um post, mostrar:
- nome de quem comentou
- comentário completo

## Tratamento de erro
Como o cliente pediu uma experiência mais amigável, o ideal é evitar mensagens técnicas na tela.

Exemplos de mensagens gentis:
- “Não foi possível carregar os dados agora. Tente novamente depois de alguns minutos.”
- “Ocorreu um problema ao buscar os posts deste usuário.”
- “Não foi possível carregar os comentários deste post.”
