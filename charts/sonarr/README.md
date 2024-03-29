# sonarr

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 3.0.10.1567](https://img.shields.io/badge/AppVersion-3.0.10.1567-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s.github.io/helm-charts/ | common | 2.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.image.repository | string | `"ghcr.io/onedr0p/sonarr"` | Image repository for Sonarr |
| controllers.main.containers.main.image.tag | string | `"3.0.10.1567"` | Image version |
| controllers.main.containers.main.probes | object | `{"liveness":{"custom":true,"enabled":true,"spec":{"exec":{"command":["/usr/bin/env","bash","-c","curl --fail localhost:8989/api/v3/system/status?apiKey=`IFS=\\> && while read -d \\< E C; do if [[ $E = \"ApiKey\" ]]; then echo $C; fi; done < /config/config.xml`"]},"failureThreshold":5,"initialDelaySeconds":60,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":10}}}` | Custom liveness probe for Sonarr |
| controllers.main.containers.main.securityContext | object | `{"runAsGroup":0,"runAsUser":0}` | Custom security context for the container to access mounted pods (necessary for Longhorn) |
| controllers.main.type | string | `"statefulset"` | Sonarr depends on a local SQLite database and thus needs to be configured as a StatefulSet |
| service.main.ports.http.port | int | `8989` | Sonarr listening port |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.12.0](https://github.com/norwoodj/helm-docs/releases/v1.12.0)
