# Grafana Setup Using Tekton
This document provides a guide to setting up Grafana using Tekton Pipelines, along with the necessary Kubernetes resources.

Overview
Grafana is a powerful open-source analytics and monitoring solution that integrates with various data sources. This setup includes a ConfigMap for Grafana configuration, a PersistentVolumeClaim (PVC) for storing Grafana data, and a Tekton Task to run Grafana with the provided configuration.

## Prerequisites
A running Kubernetes cluster (e.g., Minikube, GKE, etc.)
kubectl command-line tool configured to interact with your cluster
Tekton Pipelines installed in your cluster
Files Required
1. ConfigMap for Grafana Configuration
2. PersistentVolumeClaim for Grafana Data
3. Service for Grafana Access
4. Tekton Task for Running Grafana
5. Tekton TaskRun for Running Grafana
6. Make a service file to use Grafana

## Applying the Files

### Create the ConfigMap:

Save the ConfigMap YAML into a file named grafana-config.yaml and apply it:

kubectl apply -f grafana-configmap.yaml


### Create the PersistentVolumeClaim:

Save the PVC YAML into a file named grafana-pvc.yaml and apply it:


kubectl apply -f grafana-pvc.yaml

### Create the Tekton Task:

Save the Tekton Task YAML into a file named run-grafana.yaml and apply it:


kubectl apply -f grafana-task.yaml

### Create the Tekton TaskRun:

Save the Tekton TaskRun YAML into a file named run-grafana-run.yaml and apply it:

kubectl apply -f grafana-taskrun.yaml

### Create the Grafana Service:

Save the Service YAML into a file named grafana-service.yaml and apply it:

kubectl apply -f grafana-service.yaml

### Accessing Grafana

Once Grafana is running, you can access it by port-forwarding the Grafana service:
Apply this command on your terminal.

kubectl port-forward svc/grafana-service 3000:3000

Now you can access Grafana at http://localhost:3000.

## Conclusion
By following the steps outlined in this documentation, you will successfully set up a Grafana server using Tekton and be able to customize the configuration as needed. Make sure to adjust any parameters according to your specific requirements.