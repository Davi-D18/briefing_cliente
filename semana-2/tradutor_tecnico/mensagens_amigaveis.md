# Mensagens Amigáveis para Falhas na API

Conjunto de mensagens prontas para serem exibidas no painel quando a API JSONPlaceholder retornar algum problema ou resposta vazia. O objetivo é traduzir respostas técnicas em comunicações claras, educadas e fáceis de entender pelo usuário final.

---

## Princípio geral

Sempre traduzir problemas técnicos em mensagens humanas. O usuário final nunca deve ver:

- códigos de erro (404, 500, etc.);
- nomes técnicos da API;
- detalhes da requisição;
- stack trace;
- mensagens internas do sistema;
- termos como *endpoint*, *rota inválida*, *status 404* ou *status 500*.

Esses detalhes devem ficar disponíveis apenas em logs internos, para uso dos desenvolvedores.

---

## Contexto dos retornos da API

A API pode responder de três formas principais quando algo não sai como esperado:

1. **Recurso inexistente** → status `404`.
2. **Rota incorreta ou inexistente** → status `404`.
3. **Busca válida sem resultados** → status `200` com lista vazia `[]`.

Para o usuário, todos esses casos devem aparecer como mensagens claras, sem expor o código técnico.

---

## Mensagens por cenário

### 1. Usuário não encontrado

Quando o sistema tenta carregar um usuário que não existe.

- **Mensagem principal:** Usuário não encontrado.
- **Variações:**
  - Não encontramos esse usuário.
  - Esse usuário não está disponível no momento.

---

### 2. Post não encontrado

Quando o sistema tenta carregar um post que não existe.

- **Mensagem principal:** Post não encontrado.
- **Variações:**
  - Não encontramos esse post.
  - Esse conteúdo não está disponível no momento.

---

### 3. Comentários não encontrados

Quando o sistema tenta carregar comentários de um post e não há comentários disponíveis.

- **Mensagem principal:** Nenhum comentário foi encontrado para este post.
- **Variações:**
  - Este post ainda não possui comentários.
  - Não há comentários para exibir no momento.

---

### 4. Usuário sem posts

Quando a busca funciona, mas o usuário não tem posts cadastrados.

- **Mensagem principal:** Este usuário não possui posts no momento.
- **Variações:**
  - Não há posts para exibir para este usuário.
  - Esse usuário ainda não publicou nenhum post.

---

### 5. Busca sem resultados

Quando a consulta funciona, mas retorna uma lista vazia.

- **Mensagem principal:** Não encontramos resultados para exibir.
- **Variações:**
  - Sua busca não retornou nenhum resultado.
  - Não há dados disponíveis para essa consulta.

---

### 6. Rota inválida ou endereço incorreto

Quando o sistema tenta acessar uma rota que não existe.

- **Mensagem principal:** Não foi possível encontrar as informações solicitadas.
- **Variações:**
  - O conteúdo solicitado não está disponível.
  - Não conseguimos carregar essa informação.

> **Observação:** não mencionar “rota”, “endpoint”, “URL inválida” ou “erro 404” para o usuário final.

---

### 7. Erro ao carregar dados

Quando não é possível carregar as informações por algum problema na requisição.

- **Mensagem principal:** Não foi possível carregar as informações agora. Tente novamente mais tarde.
- **Variações:**
  - Tivemos um problema ao carregar os dados. Tente novamente em instantes.
  - As informações não puderam ser carregadas no momento.

---

### 8. Erro inesperado

Quando ocorre um erro não previsto pelo sistema.

- **Mensagem principal:** Algo deu errado. Tente novamente mais tarde.
- **Variações:**
  - Ocorreu um problema inesperado.
  - Não conseguimos concluir essa ação no momento.

---

## Tabela resumo

| Situação                | Quando acontece                                       | Mensagem para o usuário                                                     |
| ----------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------- |
| Usuário não encontrado  | Quando o usuário solicitado não existe                | Usuário não encontrado.                                                     |
| Post não encontrado     | Quando o post solicitado não existe                   | Post não encontrado.                                                        |
| Sem comentários         | Quando não há comentários para o post                 | Nenhum comentário foi encontrado para este post.                            |
| Usuário sem posts       | Quando o usuário não possui posts cadastrados         | Este usuário não possui posts no momento.                                   |
| Busca sem resultados    | Quando a consulta retorna uma lista vazia             | Não encontramos resultados para exibir.                                     |
| Rota inválida           | Quando o sistema tenta acessar uma rota inexistente   | Não foi possível encontrar as informações solicitadas.                      |
| Erro ao carregar dados  | Quando o sistema não consegue carregar as informações | Não foi possível carregar as informações agora. Tente novamente mais tarde. |
| Erro inesperado         | Quando ocorre um problema não previsto                | Algo deu errado. Tente novamente mais tarde.                                |

---

## Aplicação no painel

- Toda chamada à API deve ser envolvida em `try/catch` para capturar falhas de rede e respostas inesperadas.
- Antes de exibir qualquer lista, verificar se o array retornado está vazio (`[]`) e mostrar a mensagem correspondente.
- Em todos os casos, garantir que a tela nunca fique em branco: sempre apresentar uma mensagem amigável ou um estado de carregamento.
- Manter um tom educado e acolhedor, evitando culpar o usuário pelo erro.
