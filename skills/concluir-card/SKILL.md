---
name: concluir-card
description: Fecha o trabalho num card do Xquad. Use quando a pessoa disser que terminou, concluiu ou entregou um card ou tarefa do Xquad, como "terminei o XQUAD-12", "pode fechar o 12", "acabei o APP-7", "done with ABC-3". Comenta o que mudou e como testar, com o link do PR, e move o card para a próxima coluna (o cronômetro pausa).
---

# Concluir um card do Xquad

Use as ferramentas do MCP do Xquad. Leia as convenções do próprio espaço em vez de supor.

## 1. Achar o card

- Referência `SIGLA-NÚMERO`. Só o número: use a sigla que já apareceu na conversa ou no projeto; se não der para saber, pergunte.
- Sem referência nenhuma: tente pela branch atual (ex.: `fix/app-12-...` → `APP-12`).
- Chame `get_card` e `get_board` do espaço.

## 2. Reunir o que mudou

- Se a conversa está num repositório git, veja os commits da branch em relação à base (`git log`) e, se houver a CLI do GitHub, o PR (`gh pr view --json url,title,state`).
- Use também o que foi feito nesta conversa.
- Confira a descrição do card: o que foi pedido em "Testes" ou nos checklists deve aparecer no comentário.

## 3. Comentar no card

Chame `add_comment` com, em linguagem simples:
- **O que mudou**: 2 a 5 itens, do ponto de vista de quem usa;
- **Como testar**: passos curtos, na ordem;
- **PR**: o link, se houver.

Se houver checklist com itens feitos, marque com `update_checklist_item`.

## 4. Mover para a próxima coluna

- Se o espaço tiver uma página de workflow (veja com `list_pages`), siga a coluna que ela indica depois do desenvolvimento.
- Sem isso, use a coluna logo depois da `devColumn` na ordem do quadro (ex.: "Em teste", "Revisão").
- Chame `move_card`. Sair da coluna de desenvolvimento pausa o cronômetro.
- Não mova para a coluna final (ex.: "Concluído") sem a pessoa pedir: normalmente alguém testa antes.

Termine dizendo para qual coluna o card foi e o link do comentário ou do card.
