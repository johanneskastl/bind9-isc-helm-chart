# bind9

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 9.18](https://img.shields.io/badge/AppVersion-9.18-informational?style=flat-square)

A Helm chart for Bind9 using the official ISC docker image

## TL;DR
```console
$ helm repo add johanneskastl-bind9-isc https://johanneskastl.github.io/bind9-isc-helm-chart/
$ helm repo update
$ helm install bind9 johanneskastl-bind9-isc/bind9
```

## Installing the Chart
To install the chart with the release name `bind9`:
```console
helm install bind9 johanneskastl-bind9-isc/bind9
```

## Uninstalling the Chart
To uninstall the `bind9` deployment:
```console
helm uninstall bind9
```
The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,
```console
helm install bind9 \
  --namespace bind9 \
  --set mount_configuration_from_secret.secretName=my-named-configuration-secret
    johanneskastl-bind9-isc/bind9
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.
For example,
```console
helm install bind9 johanneskastl-bind9-isc/bind9 -f values.yaml
```

