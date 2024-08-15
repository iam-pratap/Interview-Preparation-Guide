`1. You have an application deployed on Kubernetes that is experiencing increased traffic. How would you scale the application to handle the increased load ?`

To scale the application, I would follow these steps:

- Identify the bottleneck: Analyze resource utilization, including CPU, memory, and network, to determine the limiting factor.
- Horizontal scaling: If the bottleneck is CPU or memory, I would scale the application horizontally by increasing the number of replicas using a Horizontal Pod Autoscaler (HPA).
- Vertical scaling: If the bottleneck is resource-specific, I would vertically scale the application by upgrading the resources allocated to each pod.
- Monitor and validate: Monitor the application’s performance after scaling to ensure the desired scalability is achieved without impacting stability.

  <img src="https://github.com/user-attachments/assets/172947ca-5634-40f3-8926-d9aeb9bfcc49" width="600" height="300">
