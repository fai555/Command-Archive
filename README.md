# Command-Archive

## git
`git reset HEAD~1 --soft`

### Change a Git commit message after a push
Use this [link](https://www.educative.io/edpresso/how-to-change-a-git-commit-message-after-a-push)

Unlike --force, which will destroy any changes someone else has pushed to the branch, --force-with-lease will abort if there was an upstream change to the repository.
```
git commit --amend -m "New message"

git push --force repository-name branch-name

git push --force-with-lease repository-name branch-name
```
## Create a VM
```
gcloud beta compute --project=<PROJECT_NAME> instances create redis-client-vm \
--zone=us-central1-a \
--machine-type=e2-medium \
--subnet=<SUBNET_NAME> \
--no-address \
--maintenance-policy=MIGRATE --service-account=<SERVICE_ACCOUNT_NAME> \
--scopes=https://www.googleapis.com/auth/cloud-platform \
--image=ubuntu-2004-focal-v20201014 --image-project=ubuntu-os-cloud \
--boot-disk-size=10GB --boot-disk-type=pd-ssd --boot-disk-device-name=redis-client-vm \
--no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --reservation-affinity=any
```
