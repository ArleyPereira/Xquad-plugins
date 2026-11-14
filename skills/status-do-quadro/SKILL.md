---
name: status-do-quadro
description: Mostra como está um quadro do Xquad. Use quando a pessoa perguntar sobre o andamento do quadro, do projeto ou da sprint no Xquad, como "como está o quadro?", "o que está em andamento no APP?", "o que falta testar?", "o que dá para subir?", "board status". Resume o que está em desenvolvimento, em teste e pronto, sem listar tudo.
---

# Status de um quadro do Xquad

Use as ferramentas do MCP do Xquad.

1. Descubra o espaço pela conversa ou pelo projeto. Na dúvida, `list_spaces` e pergunte.
2. `get_board` do espaço. Se houver sprint ativa (`activeSprint`), diga o nome e quanto falta para acabar.
3. Agrupe pelo que importa, na ordem das colunas do quadro:
   - **Em desenvolvimento**: os cards da `devColumn`, com quem está em cada um;
   - **Esperando teste ou revisão**: as colunas entre o desenvolvimento e a final;
   - **Prontos**: o que chegou na coluna final recentemente, se for útil;
   - **Atrasados**: cards com prazo vencido, se houver.
4. Mostre a referência e o título de cada card, numa linha. Não liste colunas de entrada (Backlog, A fazer) inteiras: só diga quantos cards há, a menos que a pessoa peça.
5. Se a pergunta for específica ("o que falta testar?"), responda só aquilo.

Seja breve: o objetivo é a pessoa entender o quadro em poucos segundos.
