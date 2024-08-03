# CLUSTER MANAGEMENT

### 1. Display endpoint details for the cluster’s master and services.
**$ kubectl cluster-info**
### 2. Show the Kubernetes version that is active on
the server and client
**$ kubectl version**
### 3. Get the cluster’s configuration
**$ kubectl config view**
### 4. List the available API resources
**$ kubectl api-resources**
### 5. List everything
**$ kubectl get all --all-namespaces** / kubectl get all -A

# NODE MANAGEMENT
### 1. List the nodes
**$ kubectl get node**
### 2. Update the taints on nodes
**$ kubectl taint node <node_name>**
### 3. Delete a node
**$ kubectl delete node <node_name>**

# POD MANAGEMENT

### 1. List pods
**$ kubectl get pod**
### 2. Delete a pod
**$ kubectl delete pod <pod_name>**
### 3. See detailed state of a pods
**$ kubectl describe pod <pod_name>**
### 4. Create a pod
**$ kubectl create pod <pod_name>**
### 5. Run a command for a container inside a pod
**$ kubectl exec <pod_name> -c <container_name> <command>**
### 6. Get interactive shell on a pod
**$ kubectl exec -it <pod_name> /bin/sh**
### 7. See resource usage (CPU/Memory/Storage) for pods
**$ kubectl top pod**
### 8. Add/update the annotations of a pod
$ kubectl annotate pod <pod_name> <annotation>
### 9. Add/update the label of a pod
$ kubectl label pod <pod_name>
### 10. View the list of replication controllers
$ kubectl get rc
### 11. View the list of replication controllers by
namespace
$ kubectl get rc --namespace=”<namespace_name>”
### 12. Scale a ReplicaSet
$ kubectl scale --replicas=<expected_replica_num>
replicaset <name>

# DEPLOYMENT MANAGEMENT

### 1. List the deployments
$ kubectl get deployment
### 2. Show the precise status of single or multiple
deployments.
$ kubectl describe deployment <deployment_name>
### 3. Edit and update the deployment.
$ kubectl edit deployment <deployment_name>
### 4. Create a new deployment
$ kubectl create deployment <deployment_name>
### 5. Delete a deployment
$ kubectl delete deployment <deployment_name>
### 6.Check the rollout status of a deployment
$ kubectl rollout status deployment
<deployment_name>
### 7. Display Resource usage (CPU/Memory/Storage)
for nodes
$ kubectl top node
### 8. See resource allocation per node
$ kubectl describe nodes | grep Allocated -A 5
### 9.List the pods running on a node
$ kubectl get pods -o wide | grep <node_name>
### 10. To annotate a node
$ kubectl annotate node <node_name>
### 11. Add or update the labels of a node
$ kubectl label nodes <your-node-name> <label>
### 12. Scale a Deployment
$ kubectl scale deployment <deployment-name> --
replicas=<number-of-replicas>

# SECRETS
### 1. Create a secret
$ kubectl create secret <name>
### 2. List secrets
$ kubectl get secrets
### 3. View details about secrets
$ kubectl describe secrets <name>
### 4. Delete a secret
$ kubectl delete secret <secret_name>


# SERVICES
### 1. List the services
**$ kubectl get services**
### 2. View the detailed state of a service
**$ kubectl describe services <name>**
### 3. Expose a replication controller, deployment or pod as a new Kubernetes service
**$ kubectl expose deployment [deployment_name]**
### 4. Edit/update the definition of a service
**$ kubectl edit service <name>**

# COMMON OPTIONAL FLAGS
### 1. –o Format of output. (Suppose you wanted to list all of the pods in ps output format with additional information.)
**$ kubectl get pods -o wide**
### 2. Create any resource(pod/replicaset/deployment, etc) using a yaml/json file.
**$ kubectl apply -f <xyz.yaml>**
### 3. dry run:
**$ kubectl apply -f <xyz.yaml> --dry-run=client**
### 3. dry run + yaml format: 
**$ kubectl apply -f <xyz.yaml> --dry-run=client -o yaml**
