# Monitoring-Dotnet-Sample

Sample weather service with Cadvisor, node-exporter to be scrapped by Prometheus, visualized by Grafana

## Pre-requisites
- Docker
- Minikube image
- kubectl
- [.NET 9.0](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)

## Services: [port]
- Weather-App: 5170
- cAdvisor: 8080
- Node-Exporter: 9100
- Prometheus: 9090
- Grafana: 3000 
## Usage
### Minikube (Kubernetes)
- For lines 3 - 5 use separate terminals
---
Load image into minikube
```cmd
docker build -t weather-api:latest
minikube image load weather-api:latest
```
Start up minikube and run pods
```cmd
Minikube start
kubectl apply -f .
minikube service prometheus
minikube service grafana
minikube dashboard
```
Re-deploy
```cmd
kubectl rollout restart deployment <weather-app>
```
### Docker-Compose
```cmd
docker-compose up
```

## Grafana sample dashboards

- Cluster monitoring: 315
- cAdvisor metrics: 19792
- Node exporter: 1860
