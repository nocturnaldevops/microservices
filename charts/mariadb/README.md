# mariadb

![Version: 1.0.5](https://img.shields.io/badge/Version-1.0.5-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 110.4.20](https://img.shields.io/badge/AppVersion-110.4.20-informational?style=flat-square)

The open source relational database

## Requirements
* [mysql](https://github.com/krakazyabra/microservices/wiki/Databases)

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://krakazyabra.github.io/microservices/ | common | ~0.1.13 |

## TL;DR
```console
$ helm repo add krakazyabra https://krakazyabra.github.io/microservices/
$ helm repo update
$ helm install mariadb krakazyabra/mariadb
```

## Installing the Chart
To install the chart with the release name `mariadb`:
```console
helm install mariadb krakazyabra/mariadb
```

## Uninstalling the Chart
To uninstall the `mariadb` deployment:
```console
helm uninstall mariadb
```
The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](../common/values.yaml) from the [common library](../common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,
```console
helm install mariadb \
  --set env.TZ="America/New York" \
    krakazyabra/mariadb
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.
For example,
```console
helm install mariadb krakazyabra/mariadb -f values.yaml
```

## Troubleshooting
See [Wiki](https://github.com/krakazyabra/microservices/wiki/Troubleshooting).
