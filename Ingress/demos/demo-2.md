# DEMO 2: Load Balancer Service

## Introduction
In this demo you will deploy a web app that will use the API deployed in the previous demo. Then create a LoadBalancer service to for a public facing web site 

![](.\content\d2image01.png)

### Task 1: Review Portal
First lets review the default Azure Load Balancer created when you create and AKS Cluster. 

1. In the Azure Portal navigate to the the Resource Group **mc_akstechbriefing_aks-briefing_eastus**
    

## Setup 

Create a deployement for the website consisting of 2 pods

```bash
kubectl apply -f .\deployment-webapp.yaml
```




* Review portal and show load balancer,  review some of the load balancer options
    1. navigate to RG **mc_akstechbriefing_aks-briefing_eastus**
    1. Review Config OPtions 
        1. Settings -> FrontEnd IP: currently single ip for ingress & egress
        1. Settings -> Backend Pools:  outbound manages egress from cluster nodes. Pool consists of all nodes in cluster.  
    


1. create a public load balancer
1. review changes to load balancer 
1. review created ip address 
1. add dns annotation 
        * Add dns label annotation 
    ```yaml
    metadata:
    name: demowebapi-svc
    annotations:
        service.beta.kubernetes.io/azure-dns-label-name: abc-mydomain
    ```
1. create internal load balancr


apply DNS Label 
https://docs.microsoft.com/en-us/azure/aks/static-ip#apply-a-dns-label-to-the-service