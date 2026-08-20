---
name: der_sp_indicacao_pesquisa-mcp
description: Skill da REST API do DER SP: Pesquisa de Indicação do Condutor Infrator na MCP.AI: 1 endpoint em /api/der_sp_indicacao_pesquisa. DER SP: Pesquisa de Indicação do Condutor Infrator, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DER SP: Pesquisa de Indicação do Condutor Infrator — REST API skill

Você tem acesso à **DER SP: Pesquisa de Indicação do Condutor Infrator** REST API na MCP.AI.

> DER SP: Pesquisa de Indicação do Condutor Infrator, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/der_sp_indicacao_pesquisa
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
curl -X POST https://api.mcp.ai/api/der_sp_indicacao_pesquisa/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"...","ait":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/der_sp_indicacao_pesquisa/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `der_sp_indicacao_pesquisa_consultar`

DER SP: Pesquisa de Indicação do Condutor Infrator, consulta em fonte oficial. _(POST /api/der_sp_indicacao_pesquisa/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `placa` | string | Sim | Parâmetro de consulta "placa". |
| `ait` | string | Sim | Parâmetro de consulta "ait". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_der_sp_indicacao_pesquisa` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
