## Create a Resource Group
```bash
az group create --name akstechbriefing --location eastus
```

## Create an AKS Cluster
```bash
az aks create --resource-group akstechbriefing --name aks-briefing --node-count 2 --generate-ssh-keys
```

## Connect to Cluster
1. install kubernetes cli (kubectl)
    ```bash
    az aks install-cli
    ```
1. Get credentials
    ```bash
    az aks get-credentials --resource-group akstechbriefing --name aks-briefing 
    ```

