```bash

helm search hub [chart-name]
helm search hub nginx --list-repo-url -o yaml # output w jsonie, szuka mo url

helm repo add [repo-name] [chart-url]
helm repo list
helm search repo [chart-name]  # po dodaniu repo można szukać
helm search repo [chart-name] --versions
helm install [repo-name/chart-name]  --generate-name
helm install [name] [repo-name/chart-name] -n dev # z własnym name na namespace dev
helm install [name] [repo-name/chart-name] --version=<x.x.x> -n dev  # custom version
helm install [name] [repo-name/chart-name] --values=custom_values.yaml -n dev  # własne values

helm pull --untar --version=15.0.9 bitnami/wordpress  # ściagą chart, --untar rozpakowywuje

helm show values [repo-name/chart-name]
helm uninstall [Release-name]
helm list  # pokazuje release name
```