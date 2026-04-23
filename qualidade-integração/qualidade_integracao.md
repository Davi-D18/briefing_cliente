## Qualidade e Integração 

> Responsável por revisar e consolidar todas as entregas, garantindo clareza, consistência e alinhamento com o briefing do cliente.

---

## 1. O que entendemos que o cliente quer

Com base no briefing, o cliente precisa de:

- Uma tela inicial com a lista de todos os usuários
- Ao clicar em um usuário, ver os posts que ele fez
- Ao clicar em um post, ver os comentários daquele post
- Quando algo der errado, uma mensagem gentil — sem erros técnicos na tela

O fluxo completo é: **Usuários → Posts → Comentários**

---

## 2. Checklist de Revisão

Itens verificados em cada entrega da equipe:

| # | Critério | Davi | Yure | Yasmin | Dudu |
|:-:|----------|:----:|:----:|:------:|:----:|
| 1 | Entrega alinhada com o briefing do cliente | ✅ | ✅ | ✅ | ✅ |
| 2 | Linguagem clara e sem ambiguidade | ✅ | ✅ | ✅ | ✅ |
| 3 | Campos da API conferidos com os endpoints reais | ✅ | ✅ | — | ✅ |
| 4 | Rotas corretas e com método HTTP indicado | — | ✅ | — | ✅ |
| 5 | Fluxo usuários → posts → comentários coberto | ✅ | ✅ | ✅ | ✅ |
| 6 | Tratamento de erro descrito sem linguagem técnica | ✅ | ✅ | ✅ | ✅ |
| 7 | Relacionamentos entre endpoints identificados | ✅ | ✅ | — | ✅ |

---

## 3. Análise de Consistência

### Cadeia de relacionamentos verificada

A estrutura identificada pelo **Davi** na exploração da API está corretamente refletida nas rotas do **Yure**, validada pelo **Dudu** e traduzida pela **Yasmin**:

```
users.id  →  posts.userId  →  comments.postId
```

-  **Davi** identificou os campos e os relacionamentos nos endpoints reais
- **Yure** mapeou esses relacionamentos nas rotas do tradutor técnico
-  **Dudu** revisou e validou a consistência entre os dados e as rotas
-  **Yasmin** traduziu esse fluxo em linguagem acessível para o cliente

Não foram encontradas contradições entre as entregas.

### Rotas verificadas em todos os documentos

| Rota | Davi | Yure | Yasmin | Dudu |
|------|:----:|:----:|:------:|:----:|
| `GET /users` | ✅ | ✅ | ✅ | ✅ |
| `GET /posts?userId={id}` | ✅ | ✅ | ✅ | ✅ |
| `GET /posts/{id}/comments` | ✅ | ✅ | ✅ | ✅ |

---

## 4. Pontos de Atenção

Durante a revisão, foram levantados pontos que merecem atenção na próxima etapa:

- **Paginação:** a API retorna poucos dados, mas em um cenário real será necessário lidar com paginação ou carregamento progressivo
- **Campos não exibidos:** campos como `address.geo`, `company.catchPhrase` e `company.bs` existem na API, mas não têm uso direto na interface neste momento
- **Indicador de carregamento:** ainda não foi definido se haverá um estado visual de carregamento, o que pode impactar a experiência do usuário

---

## 5. Perguntas de Esclarecimento

Perguntas cuja resposta muda diretamente decisões técnicas:

### Pergunta 1
**Quando algo der errado, você quer apenas a mensagem de aviso ou também um botão "Tentar novamente"?**

**Impacto:** define se será necessário um componente interativo com ação de retry ou apenas uma mensagem informativa.

---

### Pergunta 2
**Ao clicar em um usuário para ver os posts, você quer que a lista de usuários continue visível ou que a tela seja substituída?**

**Impacto:** define a estrutura do layout e o tipo de navegação da aplicação.

---

## 6. Síntese Final

Verificação dos requisitos do briefing:

| Requisito do cliente | Coberto? | Onde |
|----------------------|:--------:|------|
| Ver todos os usuários | ✅ | Equipe |
| Ver posts por usuário | ✅ | Equipe |
| Ver comentários por post | ✅ | Equipe |
| Mensagem amigável em erro | ✅ | Yure e Yasmin |
| Sem linguagem técnica para o usuário | ✅ | Yasmin |
