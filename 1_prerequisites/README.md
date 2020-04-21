1) Install kubectl:  
https://kubernetes.io/docs/tasks/tools/install-kubectl/

2) Install gcloud CLI:  
Ubuntu: https://cloud.google.com/sdk/docs/downloads-apt-get  
MacOS: https://cloud.google.com/sdk/docs/quickstart-macos

3) Init gcloud:
```shell script
gcloud auth login
```  

4) Connect to cluster:  
```shell script
gcloud container clusters get-credentials k8s-intro --zone europe-west1-c --project k8s-intro-tech-tuesday
```   

5) Verify k8s connection:
```shell script 
kubectl version
```  