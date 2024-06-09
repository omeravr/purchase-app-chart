# Purchase App Chart

This Helm chart deploys the Purchase App application to a Kubernetes cluster.



## Prerequisites

- Kubernetes cluster
- Helm installed (version >= 3.0)



## Installing the Chart

1. Add the Helm repository:
   ```bash```
   helm repo add my-repo https://omeravr.github.io/purchase-app-chart/


2. Update the Helm repositories:
helm repo update


3. Install the chart:
helm install my-release my-repo/my-app-chart




## Accessing the Application:

Once the chart is installed, you can access the application using the NodePort service created for the customer-facing-webserver.

To get the NodePort and the IP address of your Kubernetes node, you can use the following commands:
kubectl get nodes -o wide
and:
kubectl get svc -n default customer-facing-webserver

The output will contain the NodePort and the External-IP of your nodes. Use the External-IP and the NodePort to access the application.

For example, if the External-IP is 10.20.30.40 and the NodePort is 31000, you can access the application at:
http://10.20.30.40:31000/



## Uninstalling the Chart:

To uninstall the chart, you can use the following command:
bash
Copy code
helm uninstall my-release
