# GCP Billing

### GCP Billing para Claude, ChatGPT e agentes de IA

Google Cloud Billing BigQuery export reporting through a user-connected service account.

- 📊 **3 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `GCP Billing` e **URL** `https://api.mcp.ai/p_gcp_billing`.

### Cursor

[➕ Instalar GCP Billing no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=gcp_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9nY3BfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Instalar GCP Billing no VS Code](vscode:mcp/install?name=gcp_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_gcp_billing%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_gcp_billing
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Show GCP cost by service for the last 30 days
List the top GCP services by spend this month
Break down GCP billing by project and SKU
```

---

## 3 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `gcp_billing_list_accounts` | List GCP Billing BigQuery export credential records linked to this install. |
| `gcp_billing_cost` | Query normalized GCP Billing BigQuery export costs by day, service, project, and SKU. |
| `gcp_billing_top_services` | Query top GCP services by cost from the user's BigQuery billing export. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_gcp_billing`.


---

## Suporte

- 📧 [gcp_billing@mcp.ai](mailto:gcp_billing@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/gcp_billing-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_gcp_billing` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
