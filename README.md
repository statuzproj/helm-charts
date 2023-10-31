# statuz
This repository contains helm charts for statuz.

[Helm](https://helm.sh) must be installed to use the charts. Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.  Once Helm is set up properly, add the repository as follows:


### Add a chart helm repository
Access a Kubernetes cluster. Add statuz helm repository with follow commands:
```shell
helm repo add statuz  https://statuzproj.github.io/helm-charts
helm repo update
```

List chart and versions of statuz repository available:
```shell
helm search repo statuz
```

### Installing the chart
Export default values of statuz chart to file values.yaml:
```shell
helm show values statuz/statuz > values.yaml
```
Change the values according to the need in values.yaml file.

```shell
endpoints:
  - name: google_bd
    target:
      type: webpage
      endpoint: https://www.google.com.bdd/
      interval: 15
  - name: google_in
    target:
      type: webpage
      endpoint: https://www.google.co.in/
      interval: 30
```

Install statuz with following command
```shell
helm install statuz statuz/statuz -n statuz --values values.yaml -n NAMESPACE
```

### How to uninstall statuz
Remove application with command.

```shell
helm uninstall victoria-metrics -n NAMESPACE
```
