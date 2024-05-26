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

## Workflow Templates
[templates/workflow-templates](./templates/workflow-templates/)