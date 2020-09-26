# Helm Charts

The canonical source for Helm charts.

For more information about installing and using Helm, see the [Helm Docs](https://helm.sh/docs/). For a quick introduction to Charts, see the [Chart Guide](https://helm.sh/docs/topics/charts/).

## Repository Structure

This GitHub repository contains the source for the packaged and versioned charts released in the [Helm repository](https://repo.intellectics.io/#browse/browse:helm) (the Chart Repository).

The Charts in the `stable/` directory in the master branch of this repository match the latest packaged Chart in the Chart Repository, though there may be previous versions of a Chart available in that Chart Repository.

The purpose of this repository is to provide a place for maintaining Helm Charts, with CI processes in place for managing the releasing of Charts into the Chart Repository.

The Charts in this repository are organized into two folders:

- stable
- incubator

Stable Charts meet the criteria in the [technical requirements](CONTRIBUTING.md#technical-requirements).

Incubator Charts are those that do not meet these criteria. Having the incubator folder allows charts to be shared and improved on until they are ready to be moved into the stable folder. The charts in the `incubator/` directory can be found in the [Helm Incubator repository](https://repo.intellectics.io/#browse/browse:helm-incubator).

In order to get a Chart from incubator to stable, a pull request is needed that moves the chart folder.

## How Do I Enable the Stable Repository for Helm 3?

To add the stable Helm Charts for your local client, run `helm repo add`:

```
$ helm repo add fa https://repo.intellectics.io/repository/helm
"fa" has been added to your repositories
```

You can then run `helm search fa` to see the charts.

## How Do I Enable the Incubator Repository?

To add the Incubator charts for your local client, run `helm repo add`:

```
$ helm repo add fa-incubator https://repo.intellectics.io/repository/helm-incubator
"fa-incubator" has been added to your repositories
```

You can then run `helm search fa-incubator` to see the charts.

## How Do I Install Charts?

The default repository `stable` for Helm is located at https://kubernetes-charts.storage.googleapis.com/ and is installed by default.

For Helm Stable charts, use `helm install stable/<chart>`.  
For Finarkein stable charts, just `helm install fa/<chart>`.
For Finarkein incubator charts, use `helm install fa-incubator/<chart>`.

For more information on using Helm, refer to the [Helm documentation](https://github.com/kubernetes/helm#docs).

## Contributing to an Existing Chart

Please read [Contribution Guide](CONTRIBUTING.md) for more information on how Charts can be contributed.

## Maintaining A Chart

When someone maintains a chart they have the access to merge changes to that chart. A chart approver can merge pull requests following the directions in the [REVIEW_GUIDELINES.md](REVIEW_GUIDELINES.md) file.

## Review Process

For information related to the review procedure used by the Chart repository maintainers, see [Merge approval and release process](CONTRIBUTING.md#merge-approval-and-release-process).
