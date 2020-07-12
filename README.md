# eks_task

prerequisites
- aws cli installed
- eksctl must be configured
## steps:
run command
```
eksctl create cluster -f cluster.yml
```
```
aws eks update-kubeconfig  --name adamcluster
```
```
kubectl create ns wordpress-mysql
```
```
kubectl config set-context  --current --namespace=wordpress-mysql
```
note change efs credential in efs-prov profile
```
kubectl create -f efs-prov.yml
```
```
kubectl create -f cluster-role-binding.yml
```
```
kubectl create -f sc.yml
```
```
kubectl create -f pvc.yml
```
```
kubectl create secret generic mysql-pass  --from-literal=password=redhat
```
```
kubectl create -f mysql-deployment
```
```
kubectl create -f wordpressdeployment
```
hence mysql and wordpress will be deployed
