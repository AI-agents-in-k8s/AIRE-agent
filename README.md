This repo contains the code for the AI Agents in Kubernetes book.

* Deploy the AIRE-agent using kubectl:

```bash
kubectl apply -f AIRE-agent/aire-agent.yaml
```

* Deploy the secret for the model:

```bash
export GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
kubectl create secret generic kagent-google -n kagent  --from-literal=GOOGLE_API_KEY=$GOOGLE_API_KEY   --dry-run=client -oyaml | kubectl apply -f -
```

* Deploy the model configs using kubectl:

```bash
kubectl apply -f model-config-gemini.yaml
kubectl apply -f model-config-gemini-pro.yaml
```

Update aire-agent to use the preferred model, if necessary.

* Set the `GITHUB_PERSONAL_ACCESS_TOKEN` env var in the `github-mcp.yaml` file, then deploy the GitHub MCP server:


```bash
kubectl apply -f mcp/github-mcp.yaml
```
