# Norman's Build Pipelines
A set of Workflows designed for CI/CD

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