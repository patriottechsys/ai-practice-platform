# AI Practice Platform

Flask web application for AI readiness assessments, Claude-powered consulting chat,
document generation and roadmap/framework builders.

## LLM API key

The Anthropic API key is the shared secret `Demo-Apps-Share-API-Key` in Azure Key Vault
`kv-demo-apps-shared` (subscription "Demo Apps", resource group `rg-demo-apps-shared`).
Fetch it with:

```
az keyvault secret show --vault-name kv-demo-apps-shared --name Demo-Apps-Share-API-Key --subscription "Demo Apps" --query value -o tsv
```

Set the value as the `ANTHROPIC_API_KEY` environment variable (local `.env`, Docker Compose, or the
Render dashboard). The key is optional: without it the AI features run in fallback mode.
The model is `claude-sonnet-5-5` (override with `CLAUDE_MODEL`).
