This implementation involves deploying a project to Google Kubernetes Engine (GKE) using the kubectl command-line tool. 

## Prerequisites
- [gcloud](https://cloud.google.com/sdk/docs/install-sdk)
- [kubectl](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl)
- Additionally you must authenticate and set their Google Cloud project before deploying the manifests as explained [here](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl).

## Description

The project consists of a cluster with one node running several pods, a persistent volume claim, and two load balancers.


### Pods
The pods include a `yolo_client` for the frontend, a `yolo_backend` for the backend, and a `mongodb` for the database.
They are tagged with their respecitve labels for easy identification.
- yolo_client => layer: frontend
- yolo_backend => layer: backend
- mongodb => layer: backend

### Persistent Volume Claim
The persistent volume claim ensures that the database is persisted even after the pod is deleted and recreated. 

### Load Balancers
-  backend_service: `layer: backend` => Exposes port 80 and allows the client to connect to the backend port 8000. 
-  client_service: `layer: frontend` => Exposes the client pod to the internet and allows you to connect to the client using its external IP Address

### Service
- mongodb: `layer: backend` - A cluster IP type of service that allows the backend pod to peristently communicate with the mongodb pod. Uses the label: `layer: backend` as the selector