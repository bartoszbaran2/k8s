## Deployment

```bash

# Create a deployment YAML file
kubectl create deployment [name: nginx] --image=[image: nginx:alpine] --replicas=? --dry-run=client -o yaml > deploy.yaml

# Create a deployment in k8s
kubetcl create -f deploy.yaml

# Imperatively scale the Deployment Pods to 4
kubectl scale deployment [name: nginx] --replicas=4

# Declarative scale
vim deploy.yaml -> spec.replicas = 4
kubectl apply -f deploy.yaml 

# Change deployment image
kubectl set image deployment/nginx nginx

# Change Service`s selector
kubectl set selector svc [service-name: nginx-svc] 'role=green'

# Change context
k config set-context --current --namespace=default 

# delete all from current namespace
k delete all --all

# Create initial deployment (save config in resource`s annotations)
k create -f file.deploy.yaml --save-config

# Apply changes to a deployment (deprecated)
k apply -f file.deploy.yaml --record=true

# Update deployment annotation
k annotate deployment [name] kubernetes.io/change-cause="Change details" --overwrite=true

# Get information about a deployment
k rollout status deployment [deployment-name]
k rollout history deployment [deployment-name]
k rollout history deployment [deployment-name] --revision=2

# Rollback a Deployment
k rollout undo -f file.deployment.yaml
k rollout undo -f file.deployment.yaml --to-revision=2

# ex. zrzuca pody do yamla ale tylko pody z konkretnym obrazem 
kc get pods -o yaml | grep nginx:1.23.1-alpine

kc create namespace [name:dev]
```