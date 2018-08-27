Delete with purge release:
--------------------------

helm delete --purge service-auth

Create secret for docker registry:
----------------------------------

kubectl create secret docker-registry regcred --docker-server= --docker-username=  --docker-password= --docker-email= -n service-auth --dry-run=true -o yaml

Set default namespace:
----------------------

kubectl config set-context $(kubectl config current-context) --namespace=


In bulk:
--------

az group create --name testaks2 --location westeurope
az aks create --resource-group testaks --name myAKSCluster --node-count 1 --ssh-key-value ~/.ssh/testaks.pub
az aks get-credentials --resource-group testaks --name myAKSCluster
az aks scale --resource-group=testaks --name=myAKSCluster --node-count 2

kubectl run -it --rm aks-ssh --image=debian

docker run --name nginx -v $(pwd):/usr/share/nginx/html:ro -d -p 4242:80 nginx => Repo helm in local

kubectl get pods -o json
kubectl get pods -o json -l azure-vote-back
kubectl  -p azure-vote-back-7556ff9578-zkzkq -it exec bash
kubectl describe pods -l app=azure-vote-back
kubectl describe pods azure-vote-front-5b8878fdcd-8kkzv
kubectl scale --replicas=2 deployment/azure-vote-front
kubectl get service
kubectl create -f azure-vote.yaml
kubectl describe nodes
kubectl rollout history deployment --namespace service-auth

kubectl delete pods rmq-autoscale-6d8b885f99-z9s7n --force --grace-period=0

kubectl config set-context $(kubectl config current-context) --namespace=service-auth

kubectl create secret docker-registry regcred --docker-server= --docker-username= --docker-password= --docker-email=
kubectl cluster-info

helm init
helm install chart --name release_name
helm package rmq-autoscale/ --version 1.1
helm repo index .
helm upgrade rmq-autoscale .
helm fetch test/rmq-autoscale --version 1.0-sha256 --untar
helm search test -l

# Demo
helm package . --version 1.0-latest-prod --app-version sha256
cp /Users/romainnv/works/infrastructure-kubernetes/service-auth/service-auth-1.0-latest-prod.tgz /Users/romainnv/works/trash-k8s/helm-repo
helm repo index .
helm repo update
helm fetch test/service-auth --version 1.0-latest-prod
helm upgrade --install service-auth service-auth-1.0-latest-prod.tgz --set tag=1.3
helm fetch test/rmq-autoscale --version 1.0-latest-prod --untar
cp ~/works/infrastructure-kubernetes/config.k8s.yml .
helm upgrade --install rmq-autoscale . --set tag=latest-prod,config=config.k8s.yml
helm upgrade --install service-auth service-auth-1.0-latest-prod.tgz --set tag=1.4


curl  -XPUT localhost:8001/apis/apps/v1beta1/namespaces/service-auth/deployments/auth.test/scale -d '{  "kind": "Scale", "metadata": { "name": "auth.test", "namespace": "service-ath"}, "spec": {    "replicas": 2  }}' -H 'Content-type: application/json'


kubectl get pods -o json|jq '.items[].spec.nodeName'
