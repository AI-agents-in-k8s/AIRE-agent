This repo contains the code for the AI Agents in Kubernetes book.

1. Deploy the AIRE-agent using kubectl:

```bash
kubectl apply -f AIRE-agent/aire-agent.yaml
```

2. Deploy the secret for the model:

```bash
export GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
kubectl create secret generic kagent-google -n kagent  --from-literal=GOOGLE_API_KEY=$GOOGLE_API_KEY   --dry-run=client -oyaml | kubectl apply -f -
```

3. Deploy the model configs using kubectl:

```bash
kubectl apply -f models/
```

Update aire-agent to use the preferred model, if necessary.

4. Set the `GITHUB_PERSONAL_ACCESS_TOKEN` env var in the `github-mcp.yaml` file, then deploy the GitHub MCP server:


```bash
kubectl apply -f mcp/github-mcp.yaml
```
