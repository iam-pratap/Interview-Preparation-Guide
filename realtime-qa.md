`1. Difference between public and private subnet?`

**Public subnet**:-A public subnet has a route table that includes a route to an internet gateway. This allows resources in the subnet to access the public internet and send outbound traffic directly to it. 
**Private subnet**:-A private subnet has a route table that doesn't include a route to an internet gateway. Resources in the subnet require a Network Address Translation (NAT) device to access the public internet. 

Here are some other differences between public and private subnets:

- A server in a public subnet is accessible from the public internet, while a server in a private subnet is not.
- A server in a private subnet does not get a public IP.
- You can use a public server as a bastion (jump) host to gain access to the private network.

`2. Port no:- SSH, HTTP, HTTPS, MySQL`

SSH --> 22

HTTP --> 80

HTTPS --> 443

MySQL --> 3306

`3. How to check running and stopped containers in docker?`

for,

running container --> ps

all(running+stopped) --> ps -a

`4. How to kill process id in linux?`

kill -9 PID

`5. What are the services in kubernetes?`

ClusterIP, NodePort, Loadbalancer, Headless

`6. How to check disk usage?`

To check disk usage in Linux, you can use the df or du commands

df --> Shows how much disk space is available

du --> Shows the disk usage for individual directories and files

`7. How to change permissions of file?`

chmod

`8. How to change ownership?`

chown

`9. What are the services which distribute load across all instances?`

Load balancer

`10. How to check open ports in linux?`

netstat -tulnp

`11. How to check open ports on remote server`

telnet ipaddress:portnumber

`12. What are the policies in autoscaling?`
- Target tracking
- Simple scaling
- Step scaling
    
`13. What are the s3 Storage classes and how to change from one class to another?`

Standard, standard-IA, One-Zone, Intelligent tiering, Glaciers

Use an S3 Lifecycle configuration

If the object is larger than 5 GB, you can use an S3 Lifecycle configuration to change its storage class

`14. How to check which ports are listening in my linux server ?`

netstat --listen or netstat -l
