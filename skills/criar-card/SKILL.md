---
name: criar-card
description: Cria um card no Xquad. Use quando a pessoa pedir para criar, abrir ou registrar um card, tarefa, bug ou melhoria no Xquad, como "cria um card para o erro do login", "abre uma tarefa no APP para...", "anota isso como bug no quadro", "create a card for...". Escreve título e descrição com problema, solução e testes, e põe etiquetas, versão e responsável conforme as convenções do espaço.
---

# Criar um card no Xquad

Use as ferramentas do MCP do Xquad. As convenções são do espaço: leia antes de criar.

## 1. Entender o espaço

- Descubra o espaço pela conversa ou pelo projeto. Na dúvida, `list_spaces` e pergunte.
- `get_board`: colunas, etiquetas, membros e versões disponíveis.
- `list_pages`: se houver uma página sobre etiquetas, workflow ou como escrever cards, leia com `get_page` e siga.

## 2. Escrever o card

- **Título**: curto e específico, no idioma do espaço. Diz o resultado, não o processo (ex.: "Login com Google falha no Safari").
- **Descrição** em markdown, só com as seções que fazem sentido:
  - `## Problema`: o que acontece hoje ou o que falta, e para quem;
  - `## Solução`: o que fazer, em itens;
  - `## Testes`: como saber que ficou pronto.
- Não invente detalhes que a pessoa não deu. Se faltar algo essencial (o que é o problema, por exemplo), pergunte antes.

## 3. Criar e completar

1. `create_card` com espaço, coluna, título e descrição. Coluna: a que a pessoa disser; senão a primeira coluna de entrada do quadro (ex.: "Backlog" ou "A fazer"). Criar direto na coluna de desenvolvimento já inicia o cronômetro, então só faça isso se a pessoa disser que vai começar agora.
2. `set_card_labels`: siga a página de etiquetas, se houver (ex.: uma etiqueta de tipo e as de área). Sem página, use só etiquetas que já existem no quadro e que claramente se aplicam. Não crie etiquetas novas sem a pessoa pedir.
3. `set_card_versions`: se o espaço usa versões, a versão em andamento (a mais recente ainda não lançada), salvo outra indicação.
4. `set_card_members`: quem a pessoa indicar. Se ela disser "para mim", use o nome ou e-mail dela, se já souber; senão, pergunte.
5. Se a pessoa mandou prints ou arquivos, anexe (veja a skill `anexar-arquivo`).

Termine com a referência do card criado (ex.: `APP-31`), a coluna e as etiquetas.
