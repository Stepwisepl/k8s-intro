##### 1) Create deployment
```shell script
cat << EOF > nginx.deployment.yaml 
apiVersion: apps/v1
kind: Deployment
metadata:
  name: $USER-nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 2 # tells deployment to run 2 pods matching the template
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
EOF
```  

##### 2) Deploy 
```shell script 
kubectl apply -f nginx.deployment.yaml
```                                   

##### 3) Verify 2 pods were started (replicas: 2)
```shell script 
kubectl get pods
```             

#### 4) Expose deployment as a service
```shell script
kubectl expose deployment $USER-nginx-deployment --type=LoadBalancer
kubectl get service $USER-nginx-deployment
```                      

#### 5) Update deployment
Modify `nginx.deployment.yaml` file:
- change number of replicas from 2 to 4
- change nginx image version from 1.14.2 to  1.17.10
- run `kubectl apply -f nginx.deployment.yaml`
 
