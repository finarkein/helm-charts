# Contributing Guidelines

This document outlines the process to help get your contribution accepted.

## Sign Your Work

The sign-off is a simple line at the end of the explanation for a commit. All
commits needs to be signed. Your signature certifies that you wrote the patch or
otherwise have the right to contribute the material.

You just add a line to every git commit message:

    Signed-off-by: Joe Smith <joe.smith@example.com>

If you set your `user.name` and `user.email` git configs, you can sign your
commit automatically with `git commit -s`.

Note: If your git config information is set properly then viewing the
`git log` information for your commit will look something like this:

```
Author: Joe Smith <joe.smith@example.com>
Date:   Thu Feb 2 11:41:15 2018 -0800

    Update README

    Signed-off-by: Joe Smith <joe.smith@example.com>
```

Notice the `Author` and `Signed-off-by` lines match. If they don't
your PR will be rejected by the automated DCO check.

### Reporting a Bug in Helm

If you find issue in the Helm tool, please use the issue tracker in the [helm/helm](https://github.com/helm/helm) repository.

## How to Contribute to an Existing Chart

1. Fork this repository or create a branch in this repository, develop and test your Chart changes. Remember to sign off your commits as described in the ["Sign Your Work"](#sign-your-work) chapter.
1. Ensure your Chart changes follow the [technical](#technical-requirements) and [documentation](#documentation-requirements) guidelines, described below.
1. Submit a pull request.

**_NOTE_**: In order to make testing and merging of PRs easier, please submit changes to multiple charts in separate PRs.

### Technical Requirements

- All Chart dependencies should also be submitted independently
- Must pass the linter (`helm lint`)
- Must successfully launch with default values (`helm install .`)
  - All pods go to the running state (or NOTES.txt provides further instructions if a required value is missing e.g. [minecraft](https://github.com/helm/charts/blob/master/stable/minecraft/templates/NOTES.txt#L3))
  - All services have at least one endpoint
- Must include source GitHub repositories for images used in the Chart
- Images should not have any major security vulnerabilities
- Must be up-to-date with the latest stable Helm/Kubernetes features
  - Use Deployments in favor of ReplicationControllers
- Should follow Kubernetes best practices
  - Include Health Checks wherever practical
  - Allow configurable [resource requests and limits](http://kubernetes.io/docs/user-guide/compute-resources/#resource-requests-and-limits-of-pod-and-container)
- Provide a method for data persistence (if applicable)
- Support application upgrades
- Allow customization of the application configuration
- Provide a secure default configuration
- Do not leverage alpha features of Kubernetes
- Includes a [NOTES.txt](https://helm.sh/docs/topics/charts/#chart-license-readme-and-notes) explaining how to use the application after install
- Follows [best practices](https://helm.sh/docs/chart_best_practices/)
  (especially for [labels](https://helm.sh/docs/chart_best_practices/labels/)
  and [values](https://helm.sh/docs/chart_best_practices/values/))

### Documentation Requirements

- Must include an in-depth `README.md`, including:
  - Short description of the Chart
  - Any prerequisites or requirements
  - Customization: explaining options in `values.yaml` and their defaults
- Must include a short `NOTES.txt`, including:
  - Any relevant post-installation information for the Chart
  - Instructions on how to access the application or service provided by the Chart

### Merge Approval and Release Process

A Kubernetes Charts maintainer will review the Chart change submission, and start a validation job in the CI to verify the technical requirements of the Chart. A maintainer may add "LGTM" (Looks Good To Me) or an equivalent comment to indicate that a PR is acceptable. Any change requires at least one LGTM. No pull requests can be merged until at least one maintainer signs off with an LGTM.

Once the Chart has been merged, the release job will automatically run in the CI to package and release the Chart in the [Helm repository](https://console.cloud.google.com/storage/browser/kubernetes-charts/).

## Support Channels

Whether you are a user or contributor, official support channels include:

- GitHub issues: https://github.com/finarkein/helm/issues
- Helm GitHub issues: https://github.com/helm/charts/issues
- Slack: K8S Charts - #Charts room in the [Kubernetes Slack](http://slack.kubernetes.io/)
- Slack: Helm Users - #Helm-users room in the [Kubernetes Slack](http://slack.kubernetes.io/)
- Slack: Helm Developers - #Helm-dev room in the [Kubernetes Slack](http://slack.kubernetes.io/)
