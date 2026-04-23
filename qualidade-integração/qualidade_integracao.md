# Desafio 6 — Semana 1
## Pessoa 4 — Qualidade e Integração

> Responsável por revisar e consolidar todas as entregas, garantindo clareza, consistência e alinhamento com o briefing do cliente.

---

## 1. Checklist de Revisão

Itens verificados em cada entrega da equipe:

| # | Critério | Pessoa 1 | Pessoa 2 | Pessoa 3 |
|:-:|----------|:--------:|:--------:|:--------:|
| 1 | Entrega alinhada com o briefing do cliente | ✅ | ✅ | ✅ |
| 2 | Linguagem clara e sem ambiguidade | ✅ | ✅ | ✅ |
| 3 | Campos da API conferidos com os endpoints reais | ✅ | ✅ | — |
| 4 | Rotas corretas e com método HTTP indicado | — | ✅ | — |
| 5 | Fluxo usuários → posts → comentários coberto | ✅ | ✅ | ✅ |
| 6 | Tratamento de erro descrito sem linguagem técnica | ✅ | ✅ | ✅ |
| 7 | Relacionamentos entre endpoints identificados | ✅ | ✅ | — |

---

## 2. Análise de Consistência

### Relacionamentos entre os documentos

A cadeia de dados foi verificada e está consistente em todos os arquivos:

```
users.id → posts.userId → comments.postId
```

- A **Pessoa 1** identificou os campos e os relacionamentos nos endpoints reais
- A **Pessoa 2** mapeou esses relacionamentos nas rotas do tradutor técnico
- A **Pessoa 3** traduziu esse fluxo em linguagem acessível para o cliente

Não foram encontradas contradições entre as entregas.

### Rotas verificadas

| Rota | Presente na Pessoa 1 | Presente na Pessoa 2 | Presente na Pessoa 3 |
|------|:--------------------:|:--------------------:|:--------------------:|
| `GET /users` | ✅ | ✅ | ✅ |
| `GET /posts?userId={id}` | ✅ | ✅ | ✅ |
| `GET /posts/{id}/comments` | ✅ | ✅ | ✅ |

---

## 3. Pontos de Atenção Identificados

Durante a revisão, foram levantados os seguintes pontos que merecem atenção na próxima etapa (desenvolvimento):

- **Paginação:** a API retorna até 10 posts por usuário e 5 comentários por post. Se o cliente tiver mais dados no futuro, será necessário lidar com paginação.
- **Campos não exibidos:** campos como `address.geo`, `company.catchPhrase` e `company.bs` existem na API mas não têm uso claro no painel. Devem ser ignorados por enquanto.
- **Carregamento:** não foi definido se haverá indicador visual de carregamento (ex: spinner) enquanto os dados são buscados. Isso pode ser levantado como pergunta de esclarecimento.

---

## 4. Perguntas de Esclarecimento

Perguntas elaboradas após revisar todas as entregas e identificar o que ainda pode mudar decisões técnicas:

### Pergunta 1
**Ao navegar para os posts de um usuário, você quer que a lista de usuários continue visível na tela, ou ela some e só aparecem os posts?**

**Por que isso importa:** define se o layout será de uma única coluna (substitui o conteúdo) ou de múltiplas colunas (mantém o histórico de navegação visível). São estruturas de interface completamente diferentes.

---

### Pergunta 2
**O painel precisa funcionar bem no celular, ou será usado apenas no computador?**

**Por que isso importa:** se precisar funcionar no celular, o layout, o tamanho dos botões e a forma de exibir tabelas mudam significativamente. Isso afeta desde o design até as decisões de desenvolvimento.

---

## 5. Síntese Final

O documento consolidado cobre todos os pontos do briefing:

| Requisito do cliente | Coberto? | Onde |
|----------------------|:--------:|------|
| Ver todos os usuários | ✅ | Pessoa 1, 2 e 3 |
| Clicar em um usuário e ver seus posts | ✅ | Pessoa 1, 2 e 3 |
| Clicar em um post e ver comentários | ✅ | Pessoa 1, 2 e 3 |
| Mensagem amigável em caso de erro | ✅ | Pessoa 2 e 3 |
| Sem mensagem técnica exposta | ✅ | Pessoa 2 e 3 |

> Todas as entregas estão alinhadas entre si e com o briefing original. O documento está pronto para apresentação ao cliente.
