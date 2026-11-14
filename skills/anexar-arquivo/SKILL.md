---
name: anexar-arquivo
description: Anexa arquivos do computador (prints, imagens, PDFs, logs) a um card ou página do Xquad. Use quando a pessoa pedir para anexar, subir ou colocar um arquivo ou print num card ou página do Xquad, como "anexa esse print no APP-12", "coloca o PDF na página de deploy", "attach this screenshot to ABC-3".
---

# Anexar um arquivo no Xquad

Use as ferramentas do MCP do Xquad. Não leia o arquivo para a conversa nem converta para base64: envie direto do disco.

1. Confirme o caminho do arquivo e se ele existe.
2. Chame `create_upload_url` com `card` (ex.: `APP-12`) ou `page` (só um dos dois) e `file_name`. A resposta traz o link de envio e um comando `curl` pronto.
3. Rode o `curl`, trocando `/caminho/para/...` pelo caminho real do arquivo. O link é de uso único e vale 10 minutos; se expirar, gere outro. Limite de 10 MB; em páginas, só imagens.
4. A resposta do `curl` traz a URL do arquivo e o markdown `![nome](url)`. Para mostrar a imagem na descrição do card ou no texto da página, cole esse markdown com `update_card` ou `update_page`.

Termine dizendo onde o arquivo ficou.
