`1. What is the difference between Docker and Kubernetes ?`
   
Docker is a container platform where as kubernetes is a container orchestration environment that offers capabilities like Auto healing, Auto scaling, clustering and Enterprise level support like Load balancing.

`2. What are the main components of kubernetes architecture`

On a broad level, you can divide the kubernetes components in two parts

 i. Control Plane (API Server, Schedular, Controller Manager, C-CM, ETCD)
 
 ii. Data Plane (Kubelet, Kube-proxy, Container Runtime)

`3. What are the main differences between the Docker Swarm and Kubernetes ?`

 Docker Swarm is docker based solution and only suited for small organisations whereas Kubernetes is suited for large organisations as it offers more scalability, networking capabilities like policies and huge third party ecosyste support.

`4. What is the difference between Docker container and a kubernetes pod ?`

 A Pod in kubernetes is a runtime specification of a container. A pod provides more declarative way of defining using YAML and you can run more than one container in a pod.

`5. What is a namespace in kubernetes ?`

In kubernetes namespace is a logical isolation of resources, network policies, rbac and everything, For example, there are two projects using same k8s cluster. One project can use ns1 and other project can use ns2 without any overlap and authentication problems.

 `6. What is the role of kube-proxy ?`

 Kube-proxy works by maintaining a set of network rules on each node in the cluster, whicjh are updated dynamically as services are added or removed. When a client sends a request to a service, the request is intercepted by kube-proxy on the node where it was received. Kube-proxy then looks up the destination endpoint for the service and routes the request accordingly.

 Kube-proxy is an essential component of a kubernetes cluster, as it ensures that service can communicate with each other.

 `7. What are the different types of services within kubernetes ?`

 There are three different types of services that a user can create:
   i. Cluster IP Mode
  ii. Node Port Mode
 iii. Load Balancer Mode

 `8. What is the difference NodePort and LoadBalancer type service ?`

 When a service is created a NodePort type, the kube-proxy updates the IPTables with Node IP address and port that is chosen in the service configuration to access the pods.
 
 Where as if you create a Service as type LoadBalancer, the cloudcontrol manager creates a external load balancer IP using the underlying cloud provider logic in the C-CM. Users can access services using the external IP.

 `9. What is the role of Kubelet`

 Kubelet manages the containers that are scheduled to run on that node. It ensures that the containers are running and healthy, and that the resources they need are available.

 Kubelet communicates with the kubernetes API server to get information about the containers that should be running on the node, and then starts and stops the containers as needed to maintain the desired state. It also monitors the containers to ensure that they are running correctly, and restarts them if necessary.

 
