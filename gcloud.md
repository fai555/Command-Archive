# gcloud commands
gcloud projects list
gcloud config set project PROJECT_NAME
gcloud builds submit --tag gcr.io/PROJECT_NAME/IMAGE_NAME:TAG --timeout 1000 .
gcloud builds submit --tag gcr.io/PROJECT_NAME/IMAGE_NAME:TAG --machine-type=n1-highcpu-8 .
docker tag [SOURCE_IMAGE] [HOSTNAME]/[PROJECT-ID]/[IMAGE]:[TAG]


# deep learning VM
export INSTANCE_NAME="my-new-instance"
gcloud compute instances list
gcloud compute instances describe $INSTANCE_NAME
gcloud compute ssh $INSTANCE_NAME
gcloud compute ssh $INSTANCE_NAME -- -L 8080:localhost:8080


# kubectl
kubectl top pod memory-demo --namespace=mem-example kubectl get pod memory-demo-2 --output=yaml --namespace=mem-example

$ kubectl get pods $ kubectl get pods {POD_NAME} $ kubectl describe pods {POD_NAME}

$ kubectl scale --replicas=3 deployment nginx-deployment $ kubectl scale --replicas=3 -f my-deployment-spec.yml

gcloud container clusters get-credentials annotation-cluster --zone asia-southeast1-b --project im-mlpipeline

kubectl create namespace

