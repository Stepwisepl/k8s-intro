##### 1) Create service
```shell script       
kubectl expose pod $USER-nginx     
```

##### 2) See service IP
```shell script
kubectl get svc $USER-nginx
```                       

##### 3) See service details
```shell script 
kubectl describe svc $USER-nginx
```                                

##### 4) Expose it with Load Balancer
```shell script   
#delete previously created service
kubectl delete service/$USER-nginx
kubectl expose pod $USER-nginx --type=LoadBalancer  

#see external IP:
kubectl get svc $USER-nginx
```

##### 5) See your service in GCP:
https://console.cloud.google.com/kubernetes/discovery?authuser=1&organizationId=528753976363&project=k8s-intro-tech-tuesday

##### 6) Delete service
```shell script 
kubectl delete service/$USER-nginx
```