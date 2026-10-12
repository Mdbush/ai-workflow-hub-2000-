# Workflow example security

## Embedded key remediation — 12 October 2026

The exported workflow `workflows/0924_Code_Respondtowebhook_Process_Webhook.json` contained a complete PEM private key in its Decryption Code node. The current file now reads `WHATSAPP_FLOW_PRIVATE_KEY` from the n8n runtime environment and refuses to run without it. JSON parsing and JavaScript syntax validation do not establish operational compatibility with your n8n runtime.

Configure the key through your deployment's secret mechanism. If environment access is disabled for Code nodes, use a reviewed credential-backed node or other supported secret mechanism; do not enable broad environment access or paste keys back into the workflow export just to make this example run.

The former key remains in repository history and upstream copies. If that key was ever used in a real deployment, revoke/replace it in that deployment before use. Removing it from the current file does not make it secret again. Ownership, validity and deployment use were not verified by the audit.

These are third-party n8n examples, not tested WOC automations or Make blueprints. Configure and review credentials, webhook authentication, outbound requests, Code nodes and execution-data retention individually before importing or enabling a workflow. Keep real credentials and customer records out of public exports.
