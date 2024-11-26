# tyk-operator

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

Tyk Operator brings Full Lifecycle API Management capabilities to Kubernetes. Configure Ingress, APIs, Security Policies, Authentication, Authorization, Mediation and more - all using GitOps best practices with Custom Resources and Kubernetes-native primitives.

## How to install this chart

Add my public chart repo:

```console
helm repo add datarobot-oss https://datarobot-oss.github.io/helm-charts
```

A simple install with default values:

```console
helm install datarobot-oss/tyk-operator
```

To install the chart with the release name `my-release`:

```console
helm install my-release datarobot-oss/tyk-operator
```

To install with some set values:

```console
helm install my-release datarobot-oss/tyk-operator --set values_key1=value1 --set values_key2=value2
```

To install with custom values file:

```console
helm install my-release datarobot-oss/tyk-operator -f values.yaml
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| annotations | object | `{}` |  |
| envFrom[0].secretRef.name | string | `"tyk-operator-conf"` |  |
| envVars[0].name | string | `"TYK_HTTPS_INGRESS_PORT"` |  |
| envVars[0].value | string | `"8443"` |  |
| envVars[1].name | string | `"TYK_HTTP_INGRESS_PORT"` |  |
| envVars[1].value | string | `"8080"` |  |
| extraVolumeMounts | list | `[]` |  |
| extraVolumes | list | `[]` |  |
| fullnameOverride | string | `""` |  |
| healthProbePort | int | `8081` |  |
| hostNetwork | bool | `false` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"docker.io/tykio/tyk-operator"` |  |
| image.tag | string | `"v1.0.0"` |  |
| imagePullSecrets | list | `[]` |  |
| installCRDs | bool | `true` |  |
| keepCRDs | bool | `true` |  |
| metricsPort | int | `8080` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| podSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| podSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| podSecurityContext.runAsNonRoot | bool | `true` |  |
| rbac.image.pullPolicy | string | `"IfNotPresent"` |  |
| rbac.image.repository | string | `"gcr.io/kubebuilder/kube-rbac-proxy"` |  |
| rbac.image.tag | string | `"v0.15.0"` |  |
| rbac.port | int | `8443` |  |
| rbac.resources | object | `{}` |  |
| replicaCount | int | `3` |  |
| resources.limits.cpu | string | `"2"` |  |
| resources.limits.memory | string | `"4Gi"` |  |
| resources.requests.cpu | string | `"1"` |  |
| resources.requests.memory | string | `"1Gi"` |  |
| serviceMonitor | bool | `false` |  |
| webhookPort | int | `9443` |  |

### Prerequisites

Before installing the Operator make sure you follow this guide and complete all
steps from it, otherwise the Operator won't function properly: https://github.com/TykTechnologies/tyk-operator/blob/master/docs/installation/installation.md#tyk-operator-installation

**_NOTE_:** cert-manager is required as described [here](https://tyk.io/docs/tyk-stack/tyk-operator/installing-tyk-operator/#step-2-installing-cert-manager).
If you haven't installed `cert-manager` yet, you can install it as follows:
```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.8.0/cert-manager.yaml
```
