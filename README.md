# Norman's Build Pipelines
A set of Workflows designed for CI/CD

## Deployment
This helm chart is designed to be deployed with ArgoCD and Sealed Secrets in the manner described in [argocd-configs](https://github.com/frenoid/argocd-configs)


You can also use `helm install` to deploy but must deploy the secrets manually

## Templating notes
Note about templating: Where a workflow uses 
```gopl
{{workflow.parameters.path}}
```
 for templating it is replaced with
```gotpl
{{`{{workflow.parameters.path}}`}}
```
so that helm template treats it as a string literal.

## Argo Workflow configurations
[cm-artifact-repositories.yaml](./templates/argo-workflow-configs/cm-artifact-repositories.yaml) defines the repository configurations used for Argo Workflow

[cm-controller-configmap.yaml](./templates/argo-workflow-configs/cm-controller-configmap.yaml) defines defaults for any Workflow created in the `build-pipelines `namespace

## Secrets
[sealed-secrets](./templates/sealed-secrets/) are credentials used to connect to S3, Dockerhub and Github

## Workflow Templates
[templates/workflow-templates](./templates/workflow-templates/)