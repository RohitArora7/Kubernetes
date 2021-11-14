# Kubernetes
**Info**__________________________________________________________

**Pods**
```bash
kubeclt get pods 
kubectl get pods -A
kubectl get pods -n _namespace_
kubectl get pods -n _namespace_ | grep -i vpn                                                     //get vpn name pod from namespace
```
**Deployments**
```kube
kubectl get deployments
kubectl get deployments -A
kubectl get deployments -n _namespace_
```
**Namespaces**
```bash
kubectl get ns
```
**Services**
```bash
kubectl get svc -A
kubectl get svc --no-headers | wc -l                                                    //no. of services 
```
**Replica set**
```bash
kubectl get rs -A
```
**Nodes**
```kube
kubectl get nodes
kubectl get node -o wide
kubectl get node -o yaml
```


**Describe**_____________________________________ 
```bash
Kubectl describe pod _podname_
Kubectl describe deployments _deploymentname_ | grep -i image                      //extract what image has been used
```

**Create**__________________________________________________________
```bash
kubectl run rohit-nginx --image=nginx:alpine                                       //create pod

Kubectl create –f pod-definition.yml                                               //create deployment ,kubernetes pods  
Kubectl apply  –f pod-definition.yml                                               //create deployment ,kubernetes , mainly with files 
Kubectl create deployment _deploymentname_ --image=_imagename_                     //create deployment one line deployment creation 
Kubectl apply  –f pod-definition.yml  --namespace=dev                              //create deployment in particular namespace 
```

**Edit**_________________________________________________________ 
```bash
kubectl edit service _servicename_
Kubectl edit pod _podname_ 
```
