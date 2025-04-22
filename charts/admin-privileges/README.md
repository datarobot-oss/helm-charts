# admin-privileges

![Version: 1.0.2](https://img.shields.io/badge/Version-1.0.2-informational?style=flat-square)

Resources require admin privileged permission

## How to install this chart

Add my public chart repo:

```console
helm repo add datarobot-oss https://datarobot-oss.github.io/helm-charts
```

A simple install with default values:

```console
helm install my-release datarobot-oss/admin-privileges
```

To install with some set values:

```console
helm install my-release datarobot-oss/admin-privileges --set values_key1=value1 --set values_key2=value2
```

To install with custom values file:

```console
helm install my-release datarobot-oss/admin-privileges -f values.yaml
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| namespaceOverride | string | `nil` | namespaceOverride |

