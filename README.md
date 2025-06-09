# Serverless Workflow Workshop 

This project is used to run the [OpenShift Serverless Logic tutorial](https://redhat-scholars.github.io/serverless-workflow/osl/smart/index.html).

This project contains the following branches that track the different tutorial stages:

1. `main` reppresents the starting point
2. `phase2` adds the inventory check logic
3. `phase3` makes the workflow long running
4. `phase4` introduces the compensation logic

## Supporting Services

From phase 2 on, the workflow requires external services that are contained in this other project:

- https://github.com/dmarrazzo/order-swf-tut-svc


## Run the workflow locally in dev mode

```sh
podman kube play podman-kube-play.yaml
```

## Instanciate a new workflow

Start a new workflow with the following payload: 

```json
{
    "orderId": "1000",
    "item": "1111"
}
```