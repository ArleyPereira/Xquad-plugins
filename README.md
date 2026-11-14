# Plugins do Xquad

Trabalhe com os quadros do [Xquad](https://xquad.app) conversando com o seu agente de IA: inicie, conclua e crie cards, veja o status do quadro e anexe prints, sem sair do editor.

O login é pelo próprio Xquad (OAuth): sem token para copiar.

## O que vem no plugin

- **MCP do Xquad** já configurado (`https://xquad.app/api/mcp`).
- **Skills**, acionadas pela conversa (também viram comandos com barra):

| Skill | Exemplos de frase | O que faz |
| --- | --- | --- |
| `iniciar-card` | "iniciei o APP-12", "pega o 12" | Move para a coluna de desenvolvimento (o cronômetro começa), sugere a branch e resume o que fazer |
| `concluir-card` | "terminei o APP-12" | Comenta o que mudou e como testar, com o link do PR, e move para a próxima coluna |
| `criar-card` | "cria um card para o erro do login" | Título, descrição com problema, solução e testes, etiquetas, versão e responsável |
| `status-do-quadro` | "como está o quadro?" | O que está em andamento, em teste e pronto |
| `anexar-arquivo` | "anexa esse print no APP-12" | Envia o arquivo do disco direto para o card ou a página |

As skills seguem as convenções do seu espaço (coluna de desenvolvimento, etiquetas, versões e páginas de workflow), então servem para qualquer quadro.

## Instalar

### Claude Code

```
/plugin marketplace add ArleyPereira/Xquad-plugins
/plugin install xquad@xquad
```

Depois, em `/mcp`, escolha o Xquad e clique em **Authenticate**. O navegador abre o Xquad: entre e clique em **Permitir**.

Se você já tinha adicionado o Xquad à mão (`claude mcp add ... xquad`), remova com `claude mcp remove xquad` para não ficar com ele duplicado.

### Cursor e Codex

Em breve.

## Estrutura

```
skills/                    skills compartilhadas pelas três ferramentas
mcp.json                   MCP do Xquad (padrão Agent Plugins: Cursor e Codex)
plugin.json                manifesto no padrão Agent Plugins
.claude-plugin/            manifesto e marketplace do Claude Code
```

## Licença

MIT
