# Ferramentas

GCP Billing expõe 3 ferramentas (todas somente leitura).

### 1. `gcp_billing_list_accounts`
**Input**: `account` (opcional)

List GCP Billing BigQuery export credential records linked to this install.

### 2. `gcp_billing_cost`
**Input**: `days_back` (opcional), `start_date` (opcional), `end_date` (opcional), `account` (opcional)

Query normalized GCP Billing BigQuery export costs by day, service, project, and SKU.

### 3. `gcp_billing_top_services`
**Input**: `days_back` (opcional), `start_date` (opcional), `end_date` (opcional), `limit` (opcional), `account` (opcional)

Query top GCP services by cost from the user's BigQuery billing export.

## Prompts de exemplo

```
Show GCP cost by service for the last 30 days
List the top GCP services by spend this month
Break down GCP billing by project and SKU
```
