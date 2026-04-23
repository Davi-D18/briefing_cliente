
## 📋 Sobre o Projeto

O cliente pediu um painel simples para visualizar usuários, acessar os posts de cada um e ver os comentários de um post. Como ele não é técnico, tudo precisa ser comunicado de forma acessível — inclusive os erros, que devem aparecer com mensagens amigáveis, sem expor detalhes técnicos.

**Briefing original do cliente:**
> *"Preciso de um painel simples onde eu consiga ver meus usuários, clicar em um e ver os posts que ele fez, e se quiser, ver os comentários de um post. Ah — se algo der errado, não quero ver erro feio na tela. Me avisa de um jeito gentil."*

A equipe explorou a API [JSONPlaceholder](https://jsonplaceholder.typicode.com), mapeou as rotas necessárias, registrou a estrutura dos dados e produziu uma proposta completa.

---

## 🎯 Objetivo da Semana

Interpretar o briefing e entregar uma proposta técnica entendível por alguém não técnico, contendo:

- ✅ Registro da estrutura dos dados (exploração real dos endpoints)
- ✅ Tradutor técnico preenchido (briefing → rotas)
- ✅ Proposta ao cliente em linguagem acessível
- ✅ 2 perguntas de esclarecimento que mudam decisões técnicas
- ✅ Revisão e consolidação do documento final

---

## 🗂️ Estrutura do Repositório

```
desafio-6-semana-1/
├── README.md                        # Este arquivo
├── exploracao_api.md           # Endpoints, campos e relacionamentos
├── tradutor_tecnico.md         # Briefing traduzido em rotas técnicas
├── proposta_cliente.md       # Proposta em linguagem acessível
└── qualidade_integracao.md          # Revisão, consistência e perguntas finais
```

---

## 👥 Divisão da Equipe

| Integrante | Responsabilidade | Entregáveis |
|------------|-----------------|-------------|
| **Davi** | Exploração da API | Campos de cada endpoint, tipos de dados, relacionamentos |
| **Yure** | Tradutor Técnico | Tabela briefing → rotas, descrição técnica de cada rota |
| **Yasmin** | Proposta ao Cliente | Proposta em linguagem simples, fluxo e tratamento de erros |
| **Dudu** | Qualidade e Integração | Revisão, consistência, perguntas de esclarecimento, doc final |

---

## 🔁 Fluxo do Painel

```
Ver Usuários  →  Clicar em um Usuário  →  Ver Posts  →  Clicar em um Post  →  Ver Comentários
```

---

## 🔗 API Utilizada

[JSONPlaceholder](https://jsonplaceholder.typicode.com) — API REST gratuita para testes e prototipação.

| Ação do cliente | Método | Endpoint | O que retorna |
|-----------------|:------:|----------|--------------|
| Ver todos os usuários | `GET` | `/users` | Lista com id, name, username, email, address, phone, website, company |
| Ver posts de um usuário | `GET` | `/posts?userId={id}` | Posts filtrados pelo userId, com id, title e body |
| Ver comentários de um post | `GET` | `/posts/{id}/comments` | Comentários do post, com id, name, email e body |

### Relacionamento entre os dados

```
users.id  →  posts.userId  →  comments.postId
```

- Um usuário pode ter vários posts
- Um post pode ter vários comentários

---

## ⚠️ Tratamento de Erros

Nenhuma mensagem técnica será exibida. Em caso de falha em qualquer etapa, o usuário verá mensagens amigáveis como:

| Situação | Mensagem exibida |
|----------|-----------------|
| Falha ao carregar usuários | *"Não foi possível carregar os usuários agora. Tente novamente em alguns instantes."* |
| Falha ao carregar posts | *"Ocorreu um problema ao buscar os posts deste usuário. Tente novamente."* |
| Falha ao carregar comentários | *"Não foi possível carregar os comentários deste post. Tente novamente."* |

Todos os erros serão capturados com `try/catch`. O usuário nunca verá uma mensagem técnica.

---

## 📅 Entregáveis da Semana 1

Conforme solicitado no enunciado:

1. **Registro da estrutura dos dados** → `exploracao_api.md`
2. **Tradutor técnico preenchido** → `tradutor_tecnico.md`
3. **Proposta ao cliente** → `proposta_cliente.md`
4. **Perguntas de esclarecimento** → `qualidade_integracao.md`
