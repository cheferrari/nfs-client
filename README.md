# nfs-client
refers to https://github.com/kubernetes-incubator/external-storage/tree/master/nfs-client  
## 1.Install NFS server
every node should install the nfs-utils
```shell
yum install -y nfs-utils
```
## 2.Get the NFS-Client Provisioner files
clone the repo
```shell
git clone https://github.com/cheferrari/nfs-client.git
```
## 3.Setup authorization and deploy the provisioner
Apply the rbac.yaml and deployment.yaml
Configure the NFS-Client provisioner, replace the PROVISIONER_NAME NFS_SERVER NFS_PATH to your own value 
```shell
kubectl apply -f rbac.yaml
kubectl apply -f deployment.yaml
```
## 4.Set the NFS-Client Provisioner as the DefaultStorageClass
```shell
kubectl apply -f class.yaml
```
## 5.Test your environment
```shell
kubectl apply -f test-claim.yaml
kubectl apply -f test-pod.yaml
```

