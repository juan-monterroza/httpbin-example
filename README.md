# httpbin-example
This is the repo to host the K8s yaml files to deploy a httpbin application

## Before deploying app

### Install Minikube

```aidl
brew install minikube
```

### Install Helm

```aidl
brew install helm
```
### Setting up environment

  * Make sure docker is running in your laptop

Run the following commands:

```aidl

kubectl create ns trackunit
kubectl apply -f service.yaml -n trackunit
kubectl apply -f serviceAccount.yaml -n trackunit
kubectl apply -f deployment.yaml -n trackunit
kubectl apply -f ingress.yaml -n trackunit
kubectl port-forward service/httpbin 8080:8080 -n trackunit

```

Now you can open the webpage as http://localhost:8080

### Resources:

  * Port forwarding:
     * https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/
  * Liveness Probe:
     * https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/
  * Service:
     * https://kubernetes.io/docs/concepts/services-networking/service/
  * Service Account:
     * https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/
  * Deployments:
     * https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
  * Security best practices for Kubernetes Deployment:
     * https://kubernetes.io/blog/2016/08/security-best-practices-kubernetes-deployment/
  * Security checklist
     * https://kubernetes.io/docs/concepts/security/security-checklist/

