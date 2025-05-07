# Centralized Logging and Monitoring with ELK Stack and Prometheus

## Overview
This project sets up centralized logging using the ELK stack and monitoring with Prometheus and Grafana in Kubernetes.

## Minikube Setup

1. Start Minikube with enough memory:
   ```bash
   minikube start --memory=8192 --cpus=4
   ```

2. Enable metrics server:
   ```bash
   minikube addons enable metrics-server
   ```

3. Deploy ELK Stack:
   ```bash
   kubectl apply -f manifests/elasticsearch/
   kubectl apply -f manifests/kibana/
   kubectl apply -f manifests/logstash/
   kubectl apply -f manifests/filebeat/
   ```

4. Deploy Prometheus and Grafana:
   ```bash
   kubectl apply -f manifests/prometheus/
   kubectl apply -f manifests/grafana/
   ```

## Cloud Setup (Generic)

1. Ensure your cluster has persistent storage and ingress configured.
2. Apply the manifests as above using `kubectl`.
3. Access Kibana and Grafana via LoadBalancer or Ingress IPs.

## Notes
- You can customize dashboards in the `dashboards/` folder.
- Grafana default credentials: admin / admin

