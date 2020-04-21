##### 1) Create namespace:
```bash
export PERSONAL_NAMESPACE=$USER
kubectl create namespace $PERSONAL_NAMESPACE
```  
##### 2) Set it as a default namespace:
Save the namespace for all subsequent kubectl commands in that context
```shell script           
kubectl config set-context --current --namespace=$PERSONAL_NAMESPACE
```                                    

##### 3) Verify:
```shell script 
kubectl get pods
```              
Expected output:
```text
No resources found in rgrebski namespace.
```