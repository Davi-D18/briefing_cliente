# README - Atividade 6 - Semana 2

## Sobre a Atividade

Nesta semana, nosso foco é deixar o painel mais inteligente e amigável ao lidar com problemas. Queremos garantir que, se algo der errado, o usuário saiba exatamente o que está acontecendo em vez de dar de cara com uma tela em branco.

Estamos tratando situações como:
- Quando uma busca não encontra nada.
- Quando o sistema demora para responder (lentidão).
- Quando ocorre algum erro externo ou travamento.

## O que vamos entregar

- **Mensagens claras:** Avisos que explicam o problema de um jeito fácil de entender.
- **Status definidos:** Identificar corretamente o que causou cada erro.
- **Registro de logs:** Um histórico detalhado para nossa equipe técnica conseguir resolver os problemas rápido.

## Organização dos Arquivos

- `index.html`: O painel principal.
- `log.md`: Onde registramos os detalhes técnicos de cada erro.
- `mensagens_amigaveis.md`: Lista com os textos que aparecem para o usuário.
- `tradutor_tecnico.md`: Um guia que ajuda a entender o que cada erro técnico significa.
- `README.md`: Este arquivo de apresentação.

## Como testar

1. Abra o `index.html` no seu navegador.
2. Tente simular os erros (como pesquisar algo inexistente) para ver como o sistema responde.
3. Confira o arquivo de logs para ver como o sistema registra as falhas.

## Equipe e Responsabilidades

* **Davi:** Responsável por testar as URLs que geram falhas no navegador e anotar as respostas da API para cada tipo de erro.
* **Yure:** Responsável por criar a tabela de decisão que define o status HTTP, a mensagem que o usuário verá e o que deve ser registrado no log para cada cenário de erro.
* **Yasmin:** Responsável por escrever uma resposta para o cliente explicando, de forma simples e sem termos técnicos, como o painel se comporta quando ocorre um erro.
* **DUDU:** Responsável por revisar e integrar todas as informações, escolher qual cenário de erro será apresentado no encontro e atualizar o tradutor técnico da semana 1 com as novas decisões sobre erros.

## Conclusão

O objetivo principal aqui é não deixar o usuário na mão. Queremos um sistema que seja resiliente, transparente e fácil de usar, mesmo quando as coisas não saem como o esperado.
```
