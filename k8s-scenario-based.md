`1. You have an application deployed on Kubernetes that is experiencing increased traffic. How would you scale the application to handle the increased load ?`

To scale the application, I would follow these steps:

- Identify the bottleneck: Analyze resource utilization, including CPU, memory, and network, to determine the limiting factor.
- Horizontal scaling: If the bottleneck is CPU or memory, I would scale the application horizontally by increasing the number of replicas using a Horizontal Pod Autoscaler (HPA).
- Vertical scaling: If the bottleneck is resource-specific, I would vertically scale the application by upgrading the resources allocated to each pod.
- Monitor and validate: Monitor the application’s performance after scaling to ensure the desired scalability is achieved without impacting stability.

  <img src="https://github.com/user-attachments/assets/172947ca-5634-40f3-8926-d9aeb9bfcc49" width="600" height="300">

`2. In your Kubernetes environment, a master or worker node suddenly fails. What happens when the master or the worker node fails?`

In a Kubernetes environment:

- **Master Node Failure**: The cluster continues to operate normally. However, pod management is lost.
- **Worker Node Failure**: DNS failures may occur on the worker node, but the master node remains operational. Kubernetes handles node failures by marking them as NotReady, evicting pods, and restarting them within 1 to 7 minutes.
- The scheduler ensures uninterrupted service availability by recreating terminated pods on other healthy worker nodes.

  <img src="https://github.com/user-attachments/assets/1ccdf3c6-e553-4832-8ef7-4532bf9aee51" width="600" height="320">

` 3.Your team is planning a high-availability Kubernetes cluster. Describe the Process and Considerations for Designing a High-Availability Kubernetes Cluster.`
To create a high-availability Kubernetes cluster, we followed these steps and considerations in our previous project :

- **Multi-Master Setup**: We deployed multiple master nodes across three availability zones to ensure redundancy and fault tolerance. This setup prevents a single point of failure at the master level.
- **etcd Distribution**: We distributed etcd members across the availability zones in a similar fashion as the master nodes. This ensures data redundancy and resilience against zone failures.
- **Load Balancing**: We configured a TCP load balancer to evenly distribute API requests among the API servers. This setup eliminates the risk of a single API server becoming a bottleneck or point of failure.
- **Node Auto-Repair**: We enabled node auto-repair feature provided by Kubernetes Engine. This feature automatically detects and replaces unhealthy nodes, maintaining the desired cluster size and health without manual intervention.

  <img src="https://github.com/user-attachments/assets/43dbe81e-f46b-49df-9b0d-553091b2cafe" width="600" height="300">
