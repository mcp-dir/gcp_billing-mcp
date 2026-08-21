# GCP Billing

### GCP Billing for Claude, ChatGPT and AI agents

Google Cloud Billing BigQuery export reporting through a user-connected service account.

- 📊 **3 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `GCP Billing`, URL `https://api.mcp.ai/p_gcp_billing`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=gcp_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9nY3BfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=gcp_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_gcp_billing%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_gcp_billing
```

---

## 3 tools

| Tool | Description |
|---|---|
| `gcp_billing_list_accounts` | List GCP Billing BigQuery export credential records linked to this install. |
| `gcp_billing_cost` | Query normalized GCP Billing BigQuery export costs by day, service, project, and SKU. |
| `gcp_billing_top_services` | Query top GCP services by cost from the user's BigQuery billing export. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_gcp_billing` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
