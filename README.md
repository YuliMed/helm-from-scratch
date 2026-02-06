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

Deployment – Runs the main application with a configurable number of replicas

Service – Exposes the application internally in the cluster

DaemonSet – Ensures one pod runs on each node

Job – Executes a one-time task

CronJob – Executes a scheduled task

ConfigMap – Stores non-sensitive configuration

Secret – Stores sensitive data such as API tokens



Commands used:
Install or upgrade the chart: helm upgrade --install myapp charts/myapp

Viev release history: helm history myapp

Rollback: helm rollback myapp 1

Verification:

kubectl get all
kubectl get configmap
kubectl get secret


