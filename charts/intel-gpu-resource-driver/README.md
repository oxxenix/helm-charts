# Dynamic Resource Allocation (DRA) Intel GPU Driver Helm Chart

## The chart installs GPU resource driver:

- [GPU](https://github.com/intel/intel-resource-drivers-for-kubernetes/tree/main/doc/gpu/README.md)

More info: [Intel Resource Drivers for Kubernetes](https://github.com/intel/intel-resource-drivers-for-kubernetes/tree/main)


## Get Helm Repository Info
```
helm repo add intel https://intel.github.io/helm-charts/
helm repo update
```

You can execute `helm search repo intel` command to see pulled charts [optional].

## Install Helm Chart
When installing, update the dependencies:
```
helm dependency update
helm install intel-gpu-resource-driver intel/intel-gpu-resource-driver
```
## Upgrade Chart
```
helm upgrade intel-gpu-resource-driver intel/intel-gpu-resource-driver [flags]
```

## Uninstall Chart
```
helm uninstall intel-gpu-resource-driver --namespace intel-gpu-resource-driver
```

## Configuration
See [Customizing the Chart Before Installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing). To see all configurable options with detailed comments:

```console
helm show values intel/intel-gpu-resource-driver
```

You may also run `helm show values` on this chart's dependencies for additional options.

| Key | Type | Default |
|-----|------|---------|
| image.repository | string | `intel` |
| image.name | string | `"intel-gpu-resource-driver"` |
| image.pullPolicy | string | `"IfNotPresent"` |
| image.tag | string | `"v0.7.0"` |

> [!Note]
> When upgrading, CRDs from previous version need to be removed manually because Helm supports neither upgrading nor deleting CRDs, see: https://github.com/helm/community/blob/main/hips/hip-0011.md
