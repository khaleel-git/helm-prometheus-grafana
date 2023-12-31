# Start Minikube Cluster
```
minikube start
```
# Install Prometheus-operator
## add repos
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update
```
# Install chart
```
helm install prometheus prometheus-community/kube-prometheus-stack
```
# install chart with fixed version
```
helm install prometheus prometheus-community/kube-prometheus-stack --version "9.4.1"
```
Link to chart
[https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack]

# Afer Installing prometheus
```
kubectl get pod
kubectl get all
```

### DaemonSet: Node Exporter DaemonSet
DaemonSet will run on every single worker node
![DaemonSet Image](Screenshots/1.DaemonSet.PNG)

### Node Exporter DaemonSet
Translate Worder Node metrics to prometheus metrics like CPU, RAM, Load
![NodeExporterDaemonSet Image](Screenshots/1.NodeExporterDaemonSet.PNG)

# We have setup a monitoring stack
```
kubectl get statefulsets
```
![Monitoring Stack Image](Screenshots/Monitoring_Stack_has_been_setup.PNG)

# Access Grafana now
```
kubectl get service
```
These are Cluser Ip, they are not open for reqest, they are all closed

## Get deployment
```
kubectl get deployment
```
## Get pod ports
![Cluster IP Image](Screenshots/Cluster_IP.PNG)
```
kubectl logs promethus-grafana-67596ff846 -c grafana
kubectl port-forward svc/prometheus-grafana 3000:80
username: admin
password: prom-operator
```
![NodeExporter](Screenshots/GrafanaNodeExporter.PNG)
# Screenshots
![ConfigMaps Image](Screenshots/ConfigMaps.PNG)
![StatefulSets Image](Screenshots/statefulsets.PNG)
![ReplicaSets Image](Screenshots/ReplicaSets.PNG)
![Deployments Image](Screenshots/deployments.PNG)
![CRDs Image](Screenshots/CRDs.PNG)
![Secrets Image](Screenshots/Secrets.PNG)
![Services Image](Screenshots/Services_each_component_has_own.PNG)
![kubectl Describe Image](Screenshots/kubectl_describe.PNG)