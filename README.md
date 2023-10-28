# Start Minikube Cluster
```
minikube start
```
#Install Prometheus-operator
##add repos
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update
```
#Install chart
```
helm install prometheus prometheus-community/kube-prometheus-stack
```
# install chart with fixed version
```
helm install prometheus prometheus-community/kube-prometheus-stack --version "9.4.1"
```
Link to chart
[https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack]