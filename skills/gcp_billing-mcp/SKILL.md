---
name: gcp_billing-mcp
description: Skill da REST API do GCP Billing na MCP.AI: 3 endpoints em /api/gcp_billing. Google Cloud Billing BigQuery export reporting through a user-connected service account. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# GCP Billing — REST API skill

Você tem acesso à **GCP Billing** REST API na MCP.AI.

> Google Cloud Billing BigQuery export reporting through a user-connected service account.

## Base URL

```
https://api.mcp.ai/api/gcp_billing
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/gcp_billing/cost \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/gcp_billing/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (3)

#### `gcp_billing_cost`

Query normalized GCP Billing BigQuery export costs by day, service, project, and SKU. _(POST /api/gcp_billing/cost)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `days_back` | integer | Não | Relative range in days. |
| `start_date` | string | Não | Start date YYYY-MM-DD. |
| `end_date` | string | Não | End date YYYY-MM-DD. |
| `account` | string | Não | When multiple GCP billing export records are connected: connection id or label. See gcp_billing_list_accounts. |

#### `gcp_billing_list_accounts`

List GCP Billing BigQuery export credential records linked to this install. _(POST /api/gcp_billing/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | When multiple GCP billing export records are connected: connection id or label. See gcp_billing_list_accounts. |

#### `gcp_billing_top_services`

Query top GCP services by cost from the user's BigQuery billing export. _(POST /api/gcp_billing/top/services)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `days_back` | integer | Não | Relative range in days. |
| `start_date` | string | Não | Start date YYYY-MM-DD. |
| `end_date` | string | Não | End date YYYY-MM-DD. |
| `limit` | integer | Não |  |
| `account` | string | Não | When multiple GCP billing export records are connected: connection id or label. See gcp_billing_list_accounts. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_gcp_billing` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
