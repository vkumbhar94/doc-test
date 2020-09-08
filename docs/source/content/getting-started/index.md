---
title: "Getting Started"
date: 2017-08-12T16:20:39-07:00
draft: false
---

The simplest way to get started with Argus is to install it using [Helm](https://helm.sh/docs) version 3.

You'll need to add the LogicMonitor chart repository:

```bash
$ helm repo add logicmonitor https://logicmonitor.github.com/k8s-helm-charts
```

Now you can install the LogicMonitor Collectorset controller:

Download configuration file from for Collectorset-controller [values.yaml](https://github.com/logicmonitor/k8s-helm-charts/blob/master/collectorset-controller/values.yaml)

Add configuration parameters in configuration file.

```bash
$ helm upgrade \
  --install \
  --debug \
  --wait \
  -f csc-values.yaml \
  collectorset-controller logicmonitor/collectorset-controller
```

See the [configuration page](https://logicmonitor.github.io/k8s-argus/docs/configuration/) for a complete
list of values the Collectorset Controller helm chart supports, and their
descriptions.

> Note: The Collectorset controller should be installed only once per cluster.

Next, install Argus:

Download configuration file from for Argus [values.yaml](https://github.com/logicmonitor/k8s-helm-charts/blob/master/argus/values.yaml)

Add configuration parameters in configuration file.

```bash
    $ helm upgrade \
    --install \
    --debug \
    --wait \
    -f argus-values.yaml \
    argus logicmonitor/argus
```
See the [configuration page](https://logicmonitor.github.io/k8s-argus/docs/configuration/) for a complete
list of values the Argus helm chart supports, and their descriptions.

> Note: Argus should be installed only once per cluster.

After installation is complete, you should make sure you have [DataSources](https://logicmonitor.github.io/k8s-argus/docs/monitoring/) in your account
that will start monitoring the resources in your cluster.

# Community

- To report bugs and/or submit feature requests, use [GitHub](https://github.com/logicmonitor/k8s-argus/issues).
