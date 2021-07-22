# common

![Version: 0.1.13](https://img.shields.io/badge/Version-0.1.13-informational?style=flat-square) ![Type: library](https://img.shields.io/badge/Type-library-informational?style=flat-square)

Function library for krakazyabra's microservices

Since a lot of charts follow the same pattern this library was built to reduce maintenance cost between the charts that use it and try achieve a goal of being DRY.

## TL;DR
```console
$ helm repo add krakazyabra https://krakazyabra.github.io/microservices/
$ helm repo update
$ helm install common krakazyabra/common
```

## Creating a new chart

First be sure to checkout the many charts that already use this like [MariaDB](../mariadb/), [PostgreSQL](../postgres/) or the many others in this repository.

Include this chart as a dependency in your `Chart.yaml` e.g.

```yaml
# Chart.yaml
dependencies:
  - name: common
    version: 0.1.13
    repository: https://krakazyabra.github.io/microservices/
```
Write a `values.yaml` with some basic defaults you want to present to the user e.g.

```yaml
# Default values for node-red.

image:
  repository: ghcr.io/linuxserver/mariadb
  pullPolicy: IfNotPresent
  tag: version-110.4.20mariabionic

strategy:
  type: Recreate

# See more environment varaibles in the node-red documentation
# https://nodered.org/docs/getting-started/docker
env: {}
  # TZ:
  # NODE_OPTIONS:
  # NODE_RED_ENABLE_PROJECTS:
  # NODE_RED_ENABLE_SAFE_MODE:
  # FLOWS:

service:
  port:
    port: 3306

persistence:
  data:
    enabled: false
    emptyDir: false
    mountPath: /config
```

If not using a service, set the `service.enabled` to `false`.
```yaml
...
service:
  enabled: false
...
```

Add files to the `templates` folder.
```yaml
# templates/common.yaml
{{ include "common.all . }}

# templates/NOTES.txt
{{ include "common.notes.defaultNotes" . }}
```

If testing locally make sure you update the dependencies with:

```bash
helm dependency update
```
