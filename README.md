flux demo GitOps

Install Flux CLI by following the instructions from https://toolkit.fluxcd.io/guides/installation/#install-the-flux-cli

Variables de entorno

Replace `[...]` with the GitHub token

export GITHUB_TOKEN=[...]

Replace `[...]` with the GitHub organization or a GitHub user if it is a personal account

export GITHUB_USER=[...]

Replace `[...]` with the GitHub organization or a GitHub user if it is a personal account

export GITHUB_ORG=[...]

Replace `[...]` with `true` if it is a personal account, or with `false` if it is an GitHub organization

export GITHUB_PERSONAL=[...]

Replace `[...]` with the name repository in GitHub

export GITHUB_MULTI_CLUSTER_FLUX=[...]


```bash

Install Flux onto yours clusters
Run the bootstrap command:

# Bootstrap BLR1 cluster
kubectx blr1
flux bootstrap github \
  --owner=$GITHUB_ORG \
  --repository=$GITHUB_MULTI_CLUSTER_FLUX \
  --path=./fleet/blr1 \
  --personal

# Bootstrap SGP1 cluster
kubectx sgp1
flux bootstrap github \
  --owner=$GITHUB_ORG \
  --repository=$GITHUB_MULTI_CLUSTER_FLUX \
  --path=./fleet/sgp1 \
  --personal

```