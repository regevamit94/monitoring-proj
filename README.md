# monitoring-project
In this task, I have installed the Prometheus&Grafana on an existing gcloud cluster. I have also created my own dashboard using custom querys as for my own cluster's monitoring needs.
I have configured Variables on the project dashboard to make the dashboard more dynamic. 

## Requirements
- gcloud cli authentication.
- kubectl.


## Setup
- As mentioned above, i used an existing gcloud cluster. But if a new cluster in needed, this is how to create it with GCP cli:
  "gcloud container clusters create [CLUSTER_NAME] --zone=[ZONE] --num-nodes=[NUM_OF_NODES]"
- git clone https://github.com/regevamit94/monitoring-proj.git
- before procceed, if you wish to access the grafana dashboard from outside the cluster, you should consider edit the "grafana-service.yaml"'s type to LoaBalancer, so your cloud provider will provide EXTERNAL-IP to the service. 
- kubectl apply -f monitoring-proj/manifests/setup/
- kubectl apply -f monitoring-proj/manifests

 Grafana service port listens to port 3000. It is now accessible from outside the cluster via browser: SERVICE-EXTERNAL-IP:3000

