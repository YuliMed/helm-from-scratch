Chart structure


charts/myapp/
├── Chart.yaml
├── values.yaml
└── templates/
    ├── deployment.yaml
    ├── service.yaml
    ├── daemonset.yaml
    ├── job.yaml
    ├── cronjob.yaml
    ├── configmap.yaml
    └── secret.yaml


## Included Resources Overview

| Resource     | Purpose                                           | Common Use Case                              | Enabled by Default |
|--------------|---------------------------------------------------|----------------------------------------------|--------------------|
| Deployment   | Runs the main stateless/cron-like application     | Web/API servers, background workers          | Yes                |
| Service      | Exposes the application inside the cluster        | Internal load balancing & service discovery  | Yes                |
| DaemonSet    | Ensures exactly one pod per node                  | Node-level agents, logging, metrics collectors | No               |
| Job          | Runs a task to completion (one-off)               | Migrations, batch processing, init tasks     | No                 |
| CronJob      | Runs tasks on a schedule                          | Nightly jobs, periodic syncs, reports        | No                 |
| ConfigMap    | Stores non-sensitive configuration                | App settings, feature flags, environment     | Yes                |
| Secret       | Stores sensitive data (base64-encoded)            | Tokens, passwords, private keys              | Yes (empty)        |

## Installation

### Basic install / upgrade (recommended one-liner)

```bash


helm upgrade --install myapp ./charts/myapp \
  --namespace myapp-system \
  --create-namespace



Commands used:
Install or upgrade the chart: helm upgrade --install myapp charts/myapp

Viev release history: helm history myapp

Rollback: helm rollback myapp 1

Verification:

kubectl get all
kubectl get configmap
kubectl get secret


