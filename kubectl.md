# Rolling Update
```bash
kubectl set image deployment/frontend www=image:v2               # Rolling update "www" containers of "frontend" deployment, updating the image
kubectl rollout history deployment/frontend                      # Check the history of deployments including the revision 
kubectl rollout undo deployment/frontend                         # Rollback to the previous deployment
kubectl rollout undo deployment/frontend --to-revision=2         # Rollback to a specific revision
kubectl rollout status -w deployment/frontend                    # Watch rolling update status of "frontend" deployment until completion
kubectl rollout restart deployment/frontend                      # Rolling restart of the "frontend" deployment


cat pod.json | kubectl replace -f -                              # Replace a pod based on the JSON passed into std

# Force replace, delete and then re-create the resource. Will cause a service outage.
kubectl replace --force -f ./pod.json

# Create a service for a replicated nginx, which serves on port 80 and connects to the containers on port 8000
kubectl expose rc nginx --port=80 --target-port=8000

# Update a single-container pod's image version (tag) to v4
kubectl get pod mypod -o yaml | sed 's/\(image: myimage\):.*$/\1:v4/' | kubectl replace -f -

kubectl label pods my-pod new-label=awesome                      # Add a Label
kubectl annotate pods my-pod icon-url=http://goo.gl/XXBTWq       # Add an annotation
kubectl autoscale deployment foo --min=2 --max=10                # Auto scale a deployment "foo"

```


```sh
kubectl top pod memory-demo --namespace=mem-example
kubectl get pod memory-demo-2 --output=yaml --namespace=mem-example

kubectl get pods
kubectl get pods {POD_NAME}
kubectl describe pods {POD_NAME}
  
kubectl scale --replicas=3 deployment nginx-deployment
kubectl scale --replicas=3 -f my-deployment-spec.yml
  
gcloud container clusters get-credentials annotation-cluster --zone asia-southeast1-b --project im-mlpipeline
  
kubectl create namespace <namespace name>
```

#### Create Secrets from File
```sh
kubectl create secret generic ssl-certificates  --from-file=./src/conf.d/ssl -n web-secret --dry-run -o yaml
```

# Create backup for all the configs
Switch to the namespace which you want to backup. Then run the following command.

```sh
for OBJ in $(kubectl api-resources --verbs=list --namespaced -o name)
do
   for DEF in $(kubectl get --show-kind --ignore-not-found $OBJ -o name)
   do
      mkdir -p $(dirname $DEF)
      kubectl get $DEF -o yaml \
      | yq eval 'del(.metadata.resourceVersion, .metadata.uid, .metadata.annotations, .metadata.creationTimestamp, .metadata.selfLink, .metadata.managedFields)' - > $DEF.yaml
   done
done
```
