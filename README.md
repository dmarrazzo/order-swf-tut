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

In the Dev UI, **open** the `Workflow Definitions` page.

In workflow list, in corrispondence with _order_ workflow row, **click** on the _event icon_:

Fill in the form with the event information:

- In `Event Type` **insert**: `OrderEventType`

- **Click** `Add Header` to the right of _Event Custom Headers_ and **type** `ce-orderid` and `1000` for Header Name and Value

- In `Event Data` **copy** the following json: `{"orderId": "1000", "item": "1001"}`

Finally, **click** `Trigger` button

### Complete the workflow

To complete the workflow there are two option:

1. Send **Shipping** event:

    - In `Event Type` **insert**: `ShippingEventType`

    - **Click** `Add Header` to the right of _Event Custom Headers_ and **type** `ce-orderid` and `1000` for Header Name and Value

2. Send **Cancel** event:

    - In `Event Type` **insert**: `CancelEventType`

    - **Click** `Add Header` to the right of _Event Custom Headers_ and **type** `ce-orderid` and `1000` for Header Name and Value
