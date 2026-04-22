## Proposta ao Cliente

> Responsável por comunicar o que será entregue em linguagem clara, acessível e orientada ao valor para o cliente.
---

## 1. Proposta ao Cliente

Vamos criar um painel simples, organizado e fácil de usar, onde você poderá visualizar e acompanhar seus usuários, entendendo suas interações e atividades de forma clara e rápida.

Com poucos cliques, será possível explorar os dados de cada usuário, visualizando seus posts e comentários de maneira intuitiva, sem necessidade de conhecimento técnico.

A experiência será pensada para ser fluida, rápida e agradável, permitindo que você encontre facilmente as informações que precisa no dia a dia.

**E quando algo der errado?**
Se houver qualquer problema ao carregar os dados, seja na lista de usuários, nos posts ou nos comentários, você não verá nenhuma mensagem de erro técnicas ou confusas.

Em vez disso, será exibida uma mensagem amigável e clara, explicando o que aconteceu e orientando você a tentar novamente.

**Durante o carregamento**

Enquanto as informações estiverem sendo carregadas, será exibido um indicador visual simples, mostrando que o sistema está processando os dados e evitando qualquer sensação de lentidão ou dúvida.

---

## 2. Como será a experiência — Fluxo Principal

| Passo | O que aparece na tela | Como funciona para você |
|:-----:|-----------------------|--------------------------|
| **1** | **Tela Inicial — Lista de Usuários** | O painel abre com todos os usuários disponíveis. Para cada um, são exibidos nome, username, e-mail e cidade. |
| **2** | **Clicar em um Usuário — Ver seus Posts** | Ao clicar em qualquer usuário, o painel carrega os posts feitos por ele. Cada post mostra o título e um trecho do conteúdo. |
| **3** | **Clicar em um Post — Ver os Comentários** | Ao clicar em um post, os comentários aparecem logo abaixo, com o nome de quem comentou e o texto completo. |

---

## 3. Como lidamos com erros
Quando alguma coisa não funcionar como esperado, você verá mensagens como estas:

| Situação | Mensagem exibida ao usuário |
|----------|------------------------------|
| Falha ao carregar a lista de usuários | *"Não foi possível carregar os usuários agora. Tente novamente em alguns instantes."* |
| Falha ao carregar os posts de um usuário | *"Ocorreu um problema ao buscar os posts deste usuário. Tente novamente."* |
| Falha ao carregar os comentários de um post | *"Não foi possível carregar os comentários deste post. Tente novamente."* |

> Nenhuma mensagem técnica aparecerá. Tudo será comunicado de forma clara.

---

## 4. Perguntas de Esclarecimento

Antes de começarmos a construir, precisamos de duas respostas que vão influenciar diretamente como o painel será feito:

| # | Pergunta ao cliente | Por que essa resposta muda o que vamos construir |
|:-:|--------------------|--------------------------------------------------|
| **1** | Quando algo der errado, você quer só a mensagem de aviso ou também um botão "Tentar novamente"? | Se o botão for necessário, precisamos criar um componente de erro com ação. Se não, basta exibir o texto amigável. |
| **2** | Você quer poder pesquisar ou filtrar usuários, ou basta listar todos de uma vez? | Com filtro, precisamos de um campo de busca e lógica extra. Sem filtro, a listagem é mais simples e rápida de entregar. |

> Essas respostas não são detalhes — elas definem componentes e funcionalidades diferentes. Por isso pedimos antes de desenvolver.


---

**5. Objetivo da Solução**

O objetivo deste painel é oferecer uma experiência simples, eficiente e agradável, permitindo que você acompanhe seus usuários e suas interações sem dificuldade, economizando tempo e facilitando a tomada de decisões.