# DEMO 3: Ingress

In this demo you will deploy 2 applications then deploy an Ingress Controller and Ingress rules to route external traffic to the applications 

## Install NGINX Community edition Ingress Controller 

[NGINX Ingress Controller Options ](https://www.nginx.com/blog/guide-to-choosing-ingress-controller-part-4-nginx-ingress-controller-options/)

```bash
#NGINX Community edition
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.1/deploy/static/provider/cloud/deploy.yaml
```

Get the Ingress Controller IP Address 
```bash
kubectl get service ingress-nginx-controller --namespace=ingress-nginx -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
```