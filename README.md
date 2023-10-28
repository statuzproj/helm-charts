# statuz-helm-chart


## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repository as follows:

```shell
helm repo add statuz  https://statuzproj.github.io/helm-charts
```

Create a values.yaml file and put the endpoints you want to monitor. Here is an example values.yaml
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
helm install statuz statuz/statuz -n statuz --values values.yaml
```
