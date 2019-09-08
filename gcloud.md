# gcloud commands
>gcloud projects list
>gcloud config set project PROJECT_NAME
>gcloud builds submit --tag gcr.io/PROJECT_NAME/IMAGE_NAME:TAG --timeout 1000 .

# deep learning VM
> export INSTANCE_NAME="my-new-instance"
> gcloud compute instances list
> gcloud compute instances describe $INSTANCE_NAME
> gcloud compute ssh $INSTANCE_NAME
> gcloud compute ssh $INSTANCE_NAME -- -L 8080:localhost:8080
