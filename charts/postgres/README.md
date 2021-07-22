# postgres

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 13.3](https://img.shields.io/badge/AppVersion-13.3-informational?style=flat-square)

The World's Most Advanced Open Source Relational Database

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://krakazyabra.github.io/microservices/ | common | ~0.1.8 |

## TL;DR
```console
$ helm repo add krakazyabra https://krakazyabra.github.io/microservices/
$ helm repo update
$ helm install postgres krakazyabra/postgres
```

## Installing the Chart
To install the chart with the release name `postgres`:
```console
helm install postgres krakazyabra/postgres
```

## Uninstalling the Chart
To uninstall the `postgres` deployment:
```console
helm uninstall postgres
```
The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](../common/values.yaml) from the [common library](../common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,
```console
helm install postgres \
  --set env.TZ="America/New York" \
    krakazyabra/postgres
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.
For example,
```console
helm install postgres krakazyabra/postgres -f values.yaml
```

## Troubleshooting
See [Wiki](https://github.com/krakazyabra/microservices/wiki/Troubleshooting).