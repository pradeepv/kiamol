# A Kubernetes lab cluster in AKS

You'll need the [az](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) command installed and authenticated to your Azure subscription with the `az login` command.

## Setup

Create resource group:

```
az group create --name kiamol --location eastus
```

Create cluster:

```
az aks create -g kiamol -n kiamol-aks --node-count 1 --kubernetes-version 1.18.8
```

Get credentials to use the cluster with Kubectl:

```
az aks get-credentials --resource-group kiamol --name kiamol-aks
```

## Teardown

Delete the resource group which will remove the cluster:

```
az group delete --name kiamol 
```
