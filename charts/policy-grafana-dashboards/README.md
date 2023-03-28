# Kubernetes UI Server

[Kubernetes UI Server by AppsCode](https://github.com/kubeops/ui-server) - Kubernetes UI Server for ByteBuilders

## TL;DR;

```bash
$ helm repo add appscode https://charts.appscode.com/stable/
$ helm repo update
$ helm search repo appscode/policy-grafana-dashboards --version=v2023.03.23
$ helm upgrade -i policy-grafana-dashboards appscode/policy-grafana-dashboards -n kubeops --create-namespace --version=v2023.03.23
```

## Introduction

This chart deploys a Kubernetes UI Server on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.21+

## Installing the Chart

To install/upgrade the chart with the release name `policy-grafana-dashboards`:

```bash
$ helm upgrade -i policy-grafana-dashboards appscode/policy-grafana-dashboards -n kubeops --create-namespace --version=v2023.03.23
```

The command deploys a Kubernetes UI Server on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall the `policy-grafana-dashboards`:

```bash
$ helm uninstall policy-grafana-dashboards -n kubeops
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the `policy-grafana-dashboards` chart and their default values.

|            Parameter            |                            Description                             |      Default       |
|---------------------------------|--------------------------------------------------------------------|--------------------|
| nameOverride                    | Overrides name template                                            | <code>""</code>    |
| fullnameOverride                | Overrides fullname template                                        | <code>""</code>    |
| dashboard.enabled               |                                                                    | <code>true</code>  |
| dashboard.folderID              | ID of Grafana folder where these dashboards will be applied        | <code>0</code>     |
| dashboard.overwrite             | If true, dashboard with matching uid will be overwritten           | <code>true</code>  |
| dashboard.templatize.title      | If true, datasource will be prefixed to dashboard name             | <code>false</code> |
| dashboard.templatize.datasource | If true, datasource will be hardcoded in the dashboard             | <code>true</code>  |
| grafana.name                    | Name of Grafana Appbinding where these dashboards are applied      | <code>""</code>    |
| grafana.namespace               | Namespace of Grafana Appbinding where these dashboards are applied | <code>""</code>    |


Specify each parameter using the `--set key=value[,key=value]` argument to `helm upgrade -i`. For example:

```bash
$ helm upgrade -i policy-grafana-dashboards appscode/policy-grafana-dashboards -n kubeops --create-namespace --version=v2023.03.23 --set dashboard.folderID=0
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while
installing the chart. For example:

```bash
$ helm upgrade -i policy-grafana-dashboards appscode/policy-grafana-dashboards -n kubeops --create-namespace --version=v2023.03.23 --values values.yaml
```