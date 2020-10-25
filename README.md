[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/istio-operator)](https://artifacthub.io/packages/search?repo=istio-operator)

## Install Istio using GitOps

Istio operator manifest for installation/update of Istio using GitOps tools like Flux or ArgoCD.

This manifest was created according to ["Istio install/manage/upgrade using gitops"](https://discuss.istio.io/t/istio-install-manage-upgrade-using-gitops/6960/3) on https://discuss.istio.io


## Generate manifest for another Istio version

Download the latest/desired Istio installation. Set the `ISTIO_VERSION` (i.e. ISTIO_VERSION=1.7.3) and run command below to generate the manifest.

```sh
helm template istio-$ISTIO_VERSION/manifests/charts/istio-operator/ --set hub=docker.io/istio --set tag=$ISTIO_VERSION --set operatorNamespace=istio-operator --set istioNamespace=istio-system > istio-operator-chart/template/istio-operator-helm-install.yaml
```

## Configure a different Istio configuration profile

Update the yaml file in `istio-system/templates/istio-system.yaml` to set a different configuration profile for the Istio installation.

