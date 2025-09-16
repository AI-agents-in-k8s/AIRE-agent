This repo contains the code for the AIRE-agent. You can deploy it using kubectl or a GitOps tool like Argo.

1. Deploy the AIRE-agent using kubectl:

```bash
kubectl apply -f aire-agent.yaml
```

1. Deploy the secret for the model:

```bash
export GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
kubectl create secret generic kagent-google -n kagent  --from-literal=GOOGLE_API_KEY=$GOOGLE_API_KEY   --dry-run=client -oyaml | kubectl apply -f -
```

To deploy the model config using kubectl:

```bash
kubectl apply -f model-config.yaml
```
