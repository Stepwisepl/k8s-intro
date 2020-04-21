##### 1a) Install kubectl:  
https://kubernetes.io/docs/tasks/tools/install-kubectl/

##### 1b) Setup autocomplete for kubectl:
```shell script     
#temporary
source <(kubectl completion bash)

#or permanently
echo 'source <(kubectl completion bash)' >>~/.bashrc
```  

##### 2) Install gcloud CLI:  

Ubuntu: https://cloud.google.com/sdk/docs/downloads-apt-get  
MacOS: https://cloud.google.com/sdk/docs/quickstart-macos

##### 3) Init gcloud:
```shell script
gcloud auth login
```  

##### 4) Connect to cluster:  
```shell script
gcloud container clusters get-credentials k8s-intro --zone europe-west1-c --project k8s-intro-tech-tuesday
```   

##### 5) Verify k8s connection:
```shell script 
kubectl cluster-info   
```  
###### Sample output:
```text 
Kubernetes master is running at https://146.148.22.136
GLBCDefaultBackend is running at https://146.148.22.136/api/v1/namespaces/kube-system/services/default-http-backend:http/proxy
Heapster is running at https://146.148.22.136/api/v1/namespaces/kube-system/services/heapster/proxy
KubeDNS is running at https://146.148.22.136/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
Metrics-server is running at https://146.148.22.136/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy
```

##### 6a) Install helm:
https://helm.sh/docs/intro/install/  
Linux users - using From Script section  
MacOS users - using Homebrew

##### 6b) Setup autocomplete for helm:
```shell script
source <(helm completion bash)
```