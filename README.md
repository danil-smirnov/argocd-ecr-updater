# ArgoCD-ECR-Updater

ECR currently requires token authentication.

ArgoCD supports username and password authentication for helm repos but does not have native functionality to refresh tokens.

[This tool](https://github.com/danil-smirnov/argocd-ecr-updater) regenerates ECR tokens and updates an ArgoCD manifest with the updated token.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:
```
  helm repo add danil-smirnov https://danil-smirnov.github.io/helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
danil-smirnov` to see the charts.

To install the argocd-ecr-updater chart:
```
    helm install argocd-ecr-updater danil-smirnov/argocd-ecr-updater
```

To uninstall the chart:
```
    helm delete argocd-ecr-updater
```