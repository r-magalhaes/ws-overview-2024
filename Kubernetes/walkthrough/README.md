# Apply Frontend Pod config

- cd into the pod.yaml directory

pod.yaml

```
apiVersion: v1
kind: Pod
metadata:
  name: ws-frontend
spec:
  containers:
  - name: ws-frontend
    image: ricardomiguel/ws-fe:workshop-first
    ports:
    - containerPort: 80
```

```kubectl apply -f pod.yaml```

Check if the pod is running with

```kubectl get pods```


## Running the Frontend Deployment

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ws-frontend-deployment
  labels:
    app: ws-frontend
spec:
  replicas: 1
  selector:
    matchLabels:
      app: ws-frontend
  template:
    metadata:
      labels:
        app: ws-frontend
    spec:
      containers:
      - name: ws-frontend
        image: ricardomiguel/ws-fe:workshop-first
        ports:
        - containerPort: 80
```

```kubectl apply -f deployment.yaml```

## Running the Backend Deployment

- cd into the backend folder
- create a deployment.yaml file

```

```

```kubectl apply -f deployment.yaml```


## Setting up NginX Ingress Controller

NOTE: If you're using Minikube check the following url:

https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/


kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
