kubectl top pod memory-demo --namespace=mem-example
kubectl get pod memory-demo-2 --output=yaml --namespace=mem-example

  $ kubectl get pods
  $ kubectl get pods {POD_NAME}
  $ kubectl describe pods {POD_NAME}
  
  $ kubectl scale --replicas=3 deployment nginx-deployment
  $ kubectl scale --replicas=3 -f my-deployment-spec.yml
  
  gcloud container clusters get-credentials annotation-cluster --zone asia-southeast1-b --project im-mlpipeline
  
  kubectl create namespace <namespace name>
