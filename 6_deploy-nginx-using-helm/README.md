##### 1) Intro to helm Add bitnami chart repo to helm

##### 2) Add bitnami chart repo
```shell script            
helm repo add bitnami https://charts.bitnami.com/bitnami
```

##### 3) Find nginx chart
```shell script            
helm search repo nginx
```       

##### 4) See nginx helm chart documentation and possible values
https://github.com/bitnami/charts/tree/master/bitnami/nginx

##### 5) Deploy nginx
```shell script 
helm install $USER-nginx-helm bitnami/nginx -f nginx-values.yaml
```                                                             

See output message and wait for nginx to deploy

##### 6) Update deployment
Edit `nginx-values.yaml` change:  
replicaCount from `1` to `3`  

```shell script
helm upgrade $USER-nginx-helm bitnami/nginx -f nginx-values.yaml --description "replicaCount set to 3"
```
Wait for deployment to finish and open main paga 
 
##### 7) See deployment history:
```shell script 
helm history $USER-nginx-helm
```

##### 8) Rollback to revision 1
```shell script
helm rollback $USER-nginx-helm 1
```
