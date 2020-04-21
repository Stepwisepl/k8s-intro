##### 1) Create pod configuration file:

```shell script
cat << EOF > nginx.pod.yaml 
apiVersion: v1
kind: Pod
metadata:
  name: $USER-nginx 
  labels:
    app: $USER-nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
      - containerPort: 80 
EOF
```    

##### 2) See generated yaml config:
```shell script
cat nginx.pod.yaml 
```
##### 3) Check pod state:
```shell script 
kubectl apply -f nginx.pod.yaml
```                      

##### 4) See pod information:
```shell script 
kubectl describe pod $USER-nginx
```                             

##### 5) Set proxy to your pod:
```shell script
kubectl port-forward $USER-nginx 6868:80
```                                                    

Open http://localhost:6868

##### 6) See logs:
```shell script
kubectl logs $USER-nginx
```             

##### 7) 'ssh' to pod
```shell script 
kubectl exec -it $USER-nginx -- bash
```

##### 8) See your pod in GCP console:
https://console.cloud.google.com/kubernetes/workload?authuser=1&organizationId=528753976363&project=k8s-intro-tech-tuesday

