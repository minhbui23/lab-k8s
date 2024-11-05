# Lab 1: Deploying Nginx on Kubernetes

## Deployment 
**Apply the Nginx Deployment and expose Nginx deployment with Service type NodePort**
```bash
kubectl apply -f nginx-deploy.yaml
```
## Accessing the Nginx Service
**Get running Pod and service**
```bash
kubectl get po,svc 
```
With these commands, you can see all of the services running and you can access the nginx-service via:
```bash
http://<Node-IP>:<Node-Port>
```

# Lab 2: Deploy Static Web