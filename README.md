# Helm Charts

The source of Helm charts for Finarkein's apps.

For more information about installing and using Helm, see the [Helm Docs](https://helm.sh/docs/). For a quick introduction to Charts, see the [Chart Guide](https://helm.sh/docs/topics/charts/).

## How Do I Enable the Stable Repository for Helm 3?

To add the stable Helm Charts for your local client, run `helm repo add`:

```
$ helm repo add fa https://helm.finarkein.com/
"fa" has been added to your repositories
```

You can then run `helm search fa` to see the charts.

## How Do I Install Charts?

The default repository `stable` for Helm is located at https://kubernetes-charts.storage.googleapis.com/ and is installed by default.

For Helm Stable charts, use `helm install stable/<chart>`.  
For Finarkein stable charts, just `helm install fa/<chart>`.

For more information on using Helm, refer to the [Helm documentation](https://github.com/kubernetes/helm#docs).

## Contributing to an Existing Chart

Please read [Contribution Guide](CONTRIBUTING.md) for more information on how Charts can be contributed.

## Maintaining A Chart

When someone maintains a chart they have the access to merge changes to that chart. A chart approver can merge pull requests following the directions in the [REVIEW_GUIDELINES.md](REVIEW_GUIDELINES.md) file.

## Review Process

For information related to the review procedure used by the Chart repository maintainers, see [Merge approval and release process](CONTRIBUTING.md#merge-approval-and-release-process).
