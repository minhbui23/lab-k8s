# Lab 1: Deploying Nginx on Kubernetes

This lab covers the steps to deploy an Nginx web server on a Kubernetes cluster using a Deployment and expose it using a NodePort Service.

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Deployment Steps](#deployment-steps)
- [Accessing the Nginx Service](#accessing-the-nginx-service)

## Overview
In this lab, we will:
1. Create a Deployment for Nginx with 2 replicas.
2. Create a NodePort Service to expose Nginx to the outside world.

## Prerequisites
- A running Kubernetes cluster.
- `kubectl` configured to interact with your cluster.

## Deployment Steps
1. **Apply the Nginx Deployment**
    ```bash
    kubectl apply -f nginx-deploy.yaml
    ```
2. **Expose Nginx Deployment with Service type NodePort**
    ```bash
    kubectl apply -f nginx-service.yaml
    ```
## Accessing the Nginx Service
1. **Get running Pod**
    ```bash
    kubectl get pod -o wide
    ```
2. **Get running service in cluster**
    ```bash
    kubectl get svc 
    ```
 With these commands you can see all of service are running and you can access to nginx-service via:
 
    ```bash
    http://<Node-IP>:<Node-Port>
    ```