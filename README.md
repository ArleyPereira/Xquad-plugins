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

No app desktop do Claude, `/plugin` abre a tela de Plugins: rode os dois comandos acima no terminal, sem a barra (`claude plugin marketplace add ...` e `claude plugin install xquad@xquad`). O app e o terminal usam a mesma configuração.

Abra uma sessão nova. Em `/mcp`, escolha **plugin:xquad:xquad** e clique em **Authenticate**. O navegador abre o Xquad: entre e clique em **Permitir**.

Já tinha o Xquad conectado à mão (`claude mcp add`, com o mesmo endereço)? O Claude Code usa essa conexão e não cria outra: as skills funcionam com ela, sem login de novo.

### Cursor

Em breve no Marketplace do Cursor. Até lá, instale como plugin local:

```bash
git clone https://github.com/ArleyPereira/Xquad-plugins.git ~/.cursor/plugins/local/xquad
```

Feche e abra o Cursor. Em **Customize › MCPs**, o **xquad** (Plugin) aparece em "Needs Attention": clique em **Authenticate** e, no navegador, em **Permitir**.

Já tinha o Xquad no `~/.cursor/mcp.json` com o mesmo endereço? O Cursor esconde o MCP do plugin enquanto essa entrada existir, mesmo desligada: remova a entrada antiga (com token) e reabra o Cursor.

### Codex (app do ChatGPT)

Em breve no diretório de plugins da OpenAI. Até lá, no terminal:

```bash
codex plugin marketplace add ArleyPereira/Xquad-plugins
codex plugin add xquad@xquad
codex mcp login xquad
```

O último comando abre o navegador: entre no Xquad e clique em **Permitir**. Depois, abra um chat novo no Codex. O app ainda não pede esse login sozinho; sem ele, o Codex não usa o Xquad.

O comando `codex` vem com o app do ChatGPT (`/Applications/ChatGPT.app/Contents/Resources/codex-cli/bin/codex`).

## In English

Xquad is a Kanban project manager (https://xquad.app). This plugin connects your AI agent to your Xquad boards through Xquad's remote MCP server (`https://xquad.app/api/mcp`), with OAuth sign-in: no API token to copy. It also adds skills, triggered by plain conversation:

- **iniciar-card** (start a card): moves it to the board's development column, which starts the time tracker, and suggests a branch name.
- **concluir-card** (finish a card): comments what changed and how to test it, with the PR link, and moves the card forward.
- **criar-card** (create a card): title and description with problem, solution and tests, following the space's label conventions.
- **status-do-quadro** (board status): what is in progress, in testing and done.
- **anexar-arquivo** (attach a file): uploads a local file to a card or page through a short-lived upload URL.

The skills read each space's own conventions (development column, labels, versions, workflow pages), so they work with any board. The first time a tool is used, your client asks you to sign in to Xquad and click **Permitir** (Allow).

Privacy policy: https://xquad.app/privacy · Terms: https://xquad.app/terms

## Estrutura

```
skills/                    skills compartilhadas pelas três ferramentas
mcp.json                   MCP do Xquad (padrão Agent Plugins: Cursor e Codex)
plugin.json                manifesto no padrão Agent Plugins
.claude-plugin/            manifesto e marketplace do Claude Code
```

## Licença

MIT
