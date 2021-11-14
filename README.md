# Kubernetes

**Pods**
```bash
kubeclt get pods 
kubectl get pods -A
kubectl get pods -n _namespace_
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
```
**Replica set**
```bash
kubectl get rs -A
```
**Nodes**
```kube
kubectl get nodes
```


**Describe**_____________________________________ 
```bash
Kubectl describe pod _podname_
Kubectl describe deployments _deploymentname_ | grep -i image         //extract what image has been used
```

