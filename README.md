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

## Testcases

| #                  | Format | Security | Target                           | Policies            |
|--------------------|--------|----------|----------------------------------|---------------------|
| [01](testcase-01/) | YAML   | API Key  | SaaS                             | -                   |
| [02](testcase-02/) | JSON   | Open     | Self-Managed, on-premises        | -                   |
| [03](testcase-03/) | JSON   | OIDC     | SaaS, Self-Managed, on-premises  | -                   |
| [04](testcase-04/) | YAML   | API Key  | Self-Managed, on-premises        | CORS                |
| [05](testcase-05/) | YAML   | API Key  | Self-Managed, on-premises        | URL rewriting       |
| [06](testcase-06/) | YAML   | API Key  | 3 envs on 1 tenant, Self-managed | -                   |
| [07](testcase-07/) | JSON   | OIDC     | 3 envs on 3 tenants, on-premises | CORS, URL rewriting |

