# Lab 1: Deploying Nginx on Kubernetes
1. **Apply the Nginx Deployment and expose Nginx deployment with Service type NodePort**
    ```bash
    kubectl apply -f nginx-deploy.yaml
    ```
2. **Get running Pod and service**
    ```bash
    kubectl get po,svc 
    ```
    With these commands, you can see all of the services running and you can access the nginx-service via:
    ```bash
    http://<Node-IP>:<Node-Port>
    ```

# Lab 2: Deploy Static Web

1. **Packaging static web1 into container and push to dockerhub**
2. **Deploy static web and expose web with NodePort service**
    ```bash
    kubectl apply -f web1.yaml
    ```
3. **Get running Pod and service**
    ```bash
    kubectl get po,svc 
    ```
    you can access my web via:
    ```bash
    http://159.223.81.210:30001/
    ```

# Lab 3: Deploy Nginx as a Reverse Proxy

1. **Packaging static web2 into container and push to dockerhub**
2. **Deploy static web and expose web with NodePort service**
    ```bash
    kubectl apply -f web2.yaml
    ```
3. **Create Configmap for Nginx proxy**
    ```bash
    kubectl create configmap nginx-config --from-file=nginx.conf
    ```
4. **Deploy nginx-proxy and expose with NodePort service**
    ```bash
    kubectl apply -f nginx-config.yaml
    ```
    You can access my web1 via:
    ```bash
    http://159.223.81.210:30000/web1/
    ```
    and web2:
    ```bash
    http://159.223.81.210:30000/web2/
    ```
