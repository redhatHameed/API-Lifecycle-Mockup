# API Lifecycle Mockup

## Setup

```sh
oc project api-lifecycle
3scale remote add $NAME https://$TOKEN@$TENANT.3scale.net/
oc create secret generic 3scale-toolbox --from-file=$HOME/.3scalerc.yaml
```

```sh
oc process -f testcase-01/setup.yaml |oc create -f -
```
