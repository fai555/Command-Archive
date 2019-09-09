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



