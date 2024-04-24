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
```

