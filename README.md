# Helm Chart for bind9

This helm chart is based on the [official ISC docker image](https://hub.docker.com/r/internetsystemsconsortium/bind9).

You need to create a secret containing valid named configuration that might look something like this:

```
apiVersion: v1
kind: Secret
metadata:
  name: my-named-configuration-secret
stringData:
  named.conf.options: |
    options {
            directory "/var/cache/bind";
            forwarders {
                 1.1.1.1;
            };
            allow-recursion {
                    192.168.1.0/24;
            };
            dnssec-validation auto;
            listen-on-v6 { any; };
    };
```

You need to provide the name of this secret in the `values.yaml` file like so:

```
[...]
mount_configuration_from_secret:
  secretName: my-named-configuration-secret
[...]
```

After that, install the helm chart like described in the chart's [README](charts/bind9/README.md).
