# gcp-associate-note

## Important commands
```
gcloud

gcloud init
gcloud auth login
gcloud config set compute/zone us-east-1a
gcloud services enable compute
gcloud deployment-manager deployments list
gcloud info [ something ]
gcloud app services set-traffic [APP_NAME] splits 2=1 --migrate
gcloud storage objects update

gcloud compute images list
gcloud compute instances list
gcloud compute instances create/start/stop/delete INSTANCE_NAME
gcloud compute snapshots list
gcloud compute disks create DISK_NAME --size=SIZE
gcloud compute disks delete DISK_NAME
gcloud compute ssh INSTANCE_NAME
gcloud compute zones list

gcloud container cluster get-credentials
gcloud container clusters create [CLUSTER_NAME] --num-nodes=4
gcloud container clusters resize [CLUSTER_NAME] --size [NUM]

gcloud iam roles update editor --project [PROJECT_ID] --stage disabled
gcloud iam roles copy ...
gcloud iam roles create viewer-role --project [PROJECT_NAME] --file [FILENAME].yaml

gcloud projects add-iam-policy-binding [PROJECT_NAME] --member "[MAIL_ADDRESS]" --role "roles/editor"
gcloud projects describe [PROJECT_ID]/[PROJECT_NAME]

gcloud config configurations create

gcloud datastore export gs://[bucket-name] --async
gcloud artifacts repositories list
```

```
kubectl

kubectl autoscale rc [NAME] --max=10 --cpu-percentage=80
kubectl delete deployment
kubectl get deployment/nodes/pods/...
kubectl expose deployment [DEPLOYMENT_NAME] --type LoadBalancer --port 80 --target-port 8080
kubectl config view
kubectl apply -f manifest.yaml
```

```
gsutil

gsutil stat gs://[BUCKET_NAME]/[OBJECT_NAME]
gsutil rewrite -s [STORAGE_CLASS] gs://[BUCKET_NAME]/[OBJECT_NAME]
gcloud storage objects update ?
gsutil acl ch -u allUsers:r gs://[BUCKET_NAME]/[FILE_NAME]
gsutil iam ch allUsers:objectViewer gs://[BUCKET_NAME]/[FILE_NAME]
gsutil versioning set on gs://[BUCKET_NAME]
gsutil mb -c nearline gs://[BUCKET_NAME]
gsutil mv // rename, move file
```

```
bq

bq query
bq show
bq ls
bq extract
bq load
bq update
```

## Services
- Big Query: Data Warehouse, analytical platform
- Cloud DNS: DNS for GCP
- Cloud Data Fusion: ETL platform
- Cloud Dataprep: Data preparation service, clean, explore data
- Cloud Dataproc: Apache Hadoop, Apache Spark
- Cloud Build: Managed CI/CD service, Jenkins, CircleCI, TravisCI
- 

## Knowledge
Network
- URL maps specify direct requests to particular services. 
- Routes are used to specify paths to destination IP addresses outside a subnet. 
- Firewall rules control the flow of traffic on a network. 
- Traces are used to understand performance characteristics of services in a distributed system.

Load Balancer / Proxy:
(Internal) HTTP(S) Load Balancing
SSL Proxy
TCP Proxy
Network TCP/UDP Load Balancing

GKE Cluster
- Single zone: single zone, sinle master
- Multi zone: multiple zones, single master
- Regional: multiple zones, multiple master

Kubernetes Services:
- Headless service is a service without a cluster IP that allows direct communication to individual pods via DNS records, commonly used for stateful applications like databases where each pod represents a unique instance.
- ClusterIP in Kubernetes is an internal virtual IP address assigned to a service for accessing pods within the cluster.
- PersistentVolume in Kubernetes is a storage abstraction that provides durable storage resources, decoupled from pods, allowing them to access and persist data across pod restarts or rescheduling events.
- NodePort in Kubernetes is a service type that exposes an application externally by allocating a static port on each node in the cluster, allowing access to the service from outside the cluster through the node's IP address and the allocated port.
- LoadBalancer in Kubernetes is a service type that provisions an external load balancer (typically from a cloud provider) to distribute incoming traffic across multiple pods in a service, enabling high availability and scalability of the application.




