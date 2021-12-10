# Kubernetes
**Info**__________________________________________

**Pods**
```bash
kubeclt get pods 
kubectl get pods -A
kubectl get pods -n _namespace_
kubectl get pods -n _namespace_ | grep -i vpn                                                     //get vpn name pod from namespace
kubectl get pods rohit-pod --show-labels                                                          //show labels also
kubectl get pod rohit-pod -o yaml                                                                 //get full pod info 
kubectl get pod -o wide                                                                           //get pod ip,node ip
kubectl get pods --all-namespaces | grep -i rohit                                                 //Find pod from all namespaces
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
kubectl config set-context $(kubectl config current-context) --namespace=rohit-ns          //switch namespace
```
### Services
```bash
kubectl get svc -A
kubectl get svc --no-headers | wc -l                                                    //no. of services 
```
**Replica set**
```bash
kubectl get rs -A
kubectl scale deployment rohit-deployment --replicas=3
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

**Create**________________________________________
```bash
kubectl run rohit-nginx --image=nginx:alpine --labels=rohit-test                  //create pod

Kubectl create –f pod-definition.yml                                               //create deployment ,kubernetes pods  
Kubectl apply  –f pod-definition.yml                                               //create deployment ,kubernetes , mainly with files 
Kubectl create deployment _deploymentname_ --image=_imagename_                     //create deployment one line deployment creation 
Kubectl apply  –f pod-definition.yml  --namespace=dev                              //create deployment in particular namespace 

kubectl create namespace rohit-ns                                                  //create namespace

kubectl expose pod rohit-pod --port                                                //create service expose at 80 Cluster IP 
```

**Edit**__________________________________________
```bash
kubectl edit service _servicename_
Kubectl edit pod _podname_ 
```
```bash
kubectl get cm -n metallb-system config -o yaml
kubectl edit cm -n metallb-system config
```

**Delete**_________________________________________
```bash
Kubectl delete deployment deployment-name
```

**SMALL QUIZ**

**1. Create ns,pod,service**
```bash
kubectl create namespace rohit-ns
kubectl run rohit-pod --image-nginx:alpine
kubectl expose pod rohit-pod --port 80                                        //target port where public will hit
kubectl edit svc rohit-pod
>type: NodePort                                                           //node port from which it is exposed to public excess
kubectl get svc -o wide 
>get expose port
kubectl get node -o wide 
>get ip
>Put the ip and port in browser
```
**2. Create a pod test-pod in namespace test-ns**
```bash
kubectl run test-pod --image:redis --restart=Never --dry-run -o yaml > pod.yaml
vi pod.yaml
> add namespace:test-ns  tag in metadata 
kubectl apply -f pod.yaml
```
**3. Expose a deployment set name , nodeport, targetport** 
```bash
kubectl expose deployment test-deployment  --type=NodePort --target-port=8080 --name test-expose --dry-run -o yaml >svc.yaml
vi svc.yaml
>under the port set nodePort:30001
kubectl apply -f svc.yaml
```
