---
name: iniciar-card
description: Começa o trabalho num card do Xquad. Use quando a pessoa disser que vai começar, pegar ou iniciar um card ou tarefa do Xquad, como "iniciei o XQUAD-12", "pega o 12", "vou começar o APP-7", "start card ABC-3". Move o card para a coluna de desenvolvimento (o cronômetro começa), sugere a branch e resume o que fazer.
---

# Iniciar um card do Xquad

Use as ferramentas do MCP do Xquad. Nunca invente colunas, etiquetas ou convenções: leia do próprio espaço.

## 1. Achar o card

- A referência é `SIGLA-NÚMERO` (ex.: `APP-12`). Se a pessoa disse só o número, use a sigla do espaço que já apareceu na conversa ou no projeto (CLAUDE.md, AGENTS.md, nomes de branch). Se não houver como saber, chame `list_spaces` e pergunte qual é o espaço.
- Chame `get_card` com a referência. Se não existir, avise e pare.

## 2. Mover para a coluna de desenvolvimento

- Chame `get_board` do espaço e leia `devColumn` (ex.: "Em andamento", "Fazendo").
- Se o card ainda não está nela, chame `move_card` para a `devColumn`. Isso inicia o cronômetro de quem está trabalhando.
- Se já está, não mova de novo: só diga que o card já estava em andamento.
- Se o espaço não tem `devColumn`, pergunte para qual coluna mover.

## 3. Sugerir a branch

- Se o espaço tiver uma página de workflow ou de convenções (veja com `list_pages`; títulos como "Workflow", "Pull requests", "Etiquetas"), siga o que ela disser sobre nomes de branch.
- Sem convenção escrita, use o tipo do card pelas etiquetas: bug → `fix/`, funcionalidade nova → `feat/`, o resto (melhoria, ajuste, documentação) → `chore/`.
- Formato: `<prefixo>/<referência em minúsculas>-<resumo-curto-do-título>`, ex.: `fix/app-12-login-com-google`.
- Se a conversa está num repositório git, ofereça criar a branch a partir da branch base que o projeto usa. Não crie sem a pessoa concordar, a menos que ela tenha pedido.

## 4. Resumir o que fazer

Em poucas linhas:
- o objetivo do card (da descrição);
- os itens de checklist e as sub-tarefas em aberto;
- os testes pedidos na descrição, se houver;
- prazo, se houver.

Termine dizendo que o card está na coluna de desenvolvimento, com o cronômetro contando, e qual branch você sugere.
