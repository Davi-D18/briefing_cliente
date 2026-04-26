# Exploração de falhas na API JSONPlaceholder

## Objetivo

Nesta etapa, eu observei o que acontece quando a API não encontra o que foi pedido ou quando a requisição não é válida.
O objetivo disso é entender como o sistema deve se comportar quando der problema, para que a tela do painel continue clara para o usuário e não mostre mensagens técnicas confusas.

A ideia principal é: **quando algo falhar, o sistema não pode “quebrar” para quem está usando**. Ele precisa avisar de um jeito simples, educado e fácil de entender.

---

## O que acontece quando dá erro

A JSONPlaceholder pode responder de formas diferentes dependendo do tipo de problema.

### 1. Quando o item pedido não existe

Exemplo: procurar um usuário que não existe.

Nesses casos, a API responde com:

* **Status 404**
* Significa que **aquele item não foi encontrado**

Em linguagem bem simples:
é como procurar um nome numa lista e ele não estar lá.

Exemplo: Isso pode acontecer quando alguém tenta acessar:

* um usuário que não existe
* um post que não existe
* comentários de um post inexistente

### 2. Quando o endereço está errado

Se a pessoa acessa uma rota que não existe, a API também responde com erro.

Nesse caso, a resposta normalmente é:

* **Status 404**
* Significa que **o caminho pedido não foi encontrado**

Em palavras mais simples:
é como tentar abrir uma porta que não existe.

Esse erro costuma acontecer quando a URL está digitada errada ou quando a rota não faz parte da API.

### 3. Quando a busca funciona, mas não encontra nada

Às vezes a rota está certa, mas não existe nenhum resultado para aquele filtro.

Nesse caso, a API pode responder com:

* **Status 200**
* e uma lista vazia: `[]`

Isso quer dizer que:

* a requisição deu certo
* mas não havia dados para mostrar

Em linguagem simples:
você procurou corretamente, mas não havia nada correspondente.

Esse cenário é importante porque **não é exatamente um erro grave**.
Só significa que não existe nenhum resultado naquele momento.

---

## O que isso significa para o painel

Pensando no painel do cliente, isso quer dizer que ele precisa ter respostas claras para cada situação.

Se não encontrar um usuário, o painel pode mostrar algo como:

* “Usuário não encontrado.”

Se não houver posts, pode mostrar:

* “Este usuário não possui posts no momento.”

Se não houver comentários, pode mostrar:

* “Nenhum comentário foi encontrado para este post.”

Se a rota der erro ou a API estiver indisponível, pode mostrar:

* “Não foi possível carregar as informações agora. Tente novamente mais tarde.”

A ideia é sempre evitar deixar a tela vazia ou mostrar mensagens técnicas como códigos e detalhes internos (Erros técnicos serão mostrados apenas para os desenvolvedores).


## Resumo dos casos observados

### Quando o recurso não existe

* A API retorna **404**
* Significa que **não encontrou o que foi pedido**

### Quando a rota está errada

* A API retorna **404**
* Significa que **o endereço não existe**

### Quando a busca existe, mas não tem resultado

* A API retorna **200** com `[]`
* Significa que **a consulta funcionou, mas não encontrou dados**

## Decisão recomendada para o painel

Para o painel do cliente, o melhor comportamento é:

* mostrar uma mensagem simples quando não houver dados
* mostrar uma mensagem educada quando houver erro
* nunca deixar a tela em branco
* nunca expor erro técnico para o usuário final

Isso deixa a experiência mais tranquila e fácil de entender.


## Resumo

Durante os testes, observei que a API pode responder de três formas principais quando algo não sai como esperado: 

- Quando o item não existe ou a rota está errada, ela devolve erro 404. 
- Quando a busca funciona, mas não encontra resultado, ela pode devolver 200 com lista vazia. 

Para o painel, isso significa que a tela não deve ficar em branco. Em vez disso, ela deve mostrar mensagens simples e amigáveis, como “não encontramos esse item” ou “não há resultados para exibir”, sem mostrar informações técnicas para o usuário.
