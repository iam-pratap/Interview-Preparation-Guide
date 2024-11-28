1. **docker run**: Create and start a new container.
```
docker run -d --name mycontainer nginx
```
Output: Container ID (e.g., "e45fd9876f54")
Explanation: This command creates and starts a new container using the
"nginx" image in the background (detached mode) with the name
"mycontainer."
2. **docker ps**: List running containers.
```
docker ps
```
 Output: List of running containers
Explanation: This command displays a list of currently running
containers along with their details such as Container ID, Image, Status,
Ports, and Names.
3. **docker images**: List available images.
```
docker images
```
Output: List of available images
Explanation: This command shows a list of images available on the
local Docker host, including their Repository, Tag, Image ID, and Size.
4. **docker pull**: Download an image from a registry.
```
docker pull ubuntu:latest
```
Output: Status messages indicating the progress of the image download
Explanation: This command downloads the latest version of the
"ubuntu" image from the Docker registry.
5. **docker stop**: Stop a running container.
```
docker stop mycontainer
```
Output: None
Explanation: This command stops the specified container with the name
"mycontainer."
6. **docker rm**: Remove a container.
```
docker rm mycontainer
```
Output: None
Explanation: This command removes the specified container with the
name "mycontainer."
7. **docker rmi**: Remove an image.
```
docker rmi nginx
```
Output: None
Explanation: This command removes the specified image with the name
"nginx" from the local Docker host.
8. **docker exec**: Run a command in a running container.
```
docker exec -it mycontainer bash
```
Output: Command prompt inside the container
Explanation: This command runs the "bash" command inside the
running container with the name "mycontainer," allowing you to interact
with the container's shell.
9. **docker logs**: Fetch the logs of a container.
```
docker logs mycontainer
```
Output: Container logs
Explanation: This command retrieves and displays the logs of the
specified container with the name "mycontainer."
10. **docker build**: Build a new image from a Dockerfile.
```
docker build -t myimage .
```
 Output: Image build process output
 Explanation: This command builds a new Docker image using the
Dockerfile present in the current directory and assigns it the name
"myimage."
11. **docker tag**: Add a tag to an image.
```
docker tag myimage myrepo/myimage:v1.0
```
 Output: None
 Explanation: This command adds a new tag ("v1.0") to the existing
image "myimage" and assigns it a new repository name
"myrepo/myimage."
12. **docker push**: Push an image to a registry.
```
docker push myrepo/myimage:v1.0
```
 Output: Status messages indicating the progress of the image push
 Explanation: This command pushes the specified image with the tag
"v1.0" to the Docker registry under the repository "myrepo/myimage."
13. **docker network ls**: List networks.
```
docker network ls
```
 Output: List of available networks
 Explanation: This command displays a list of available networks on the
Docker host, including their Network ID
, Name, Driver, and Scope.
14. **docker network create**: Create a new network.
```
docker network create mynetwork
```
 Output: Network ID (e.g., "ab12cd34ef56")
 Explanation: This command creates a new Docker network with the
name "mynetwork" using the default bridge driver.
15. **docker network connect**: Connect a container to a network.
```
docker network connect mynetwork mycontainer
```
 Output: None
 Explanation: This command connects the specified container
("mycontainer") to the network with the name "mynetwork."
16. **docker volume ls**: List volumes.
```
docker volume ls
```
 Output: List of available volumes
 Explanation: This command lists the available Docker volumes on the
host, showing their names and mount points.
17. **docker volume create**: Create a new volume.
```
docker volume create myvolume
```
 Output: Volume name (e.g., "myvolume")
 Explanation: This command creates a new Docker volume with the
name "myvolume" for persistent data storage.
18. **docker volume inspect**: Inspect a volume.
```
docker volume inspect myvolume
```
 Output: Volume details in JSON format
 Explanation: This command provides detailed information about the
specified volume, including its name, mount point, and driver.
19. **docker volume rm**: Remove a volume.
```
docker volume rm myvolume
```
 Output: None
 Explanation: This command removes the specified Docker volume with
the name "myvolume" from the host.
20. **docker-compose up**: Create and start containers defined in a
Compose file.
```
docker-compose up -d
```
Output: Status messages indicating the creation and startup of containers
Explanation: This command creates and starts containers defined in a
Docker Compose file in the background (detached mode).
21. **docker-compose down**: Stop and remove containers defined in
a Compose file.
```
docker-compose down
```
 Output: Status messages indicating the shutdown and removal of
containers
 Explanation: This command stops and removes the containers defined
in a Docker Compose file.
22. **docker-compose logs**: Fetch the logs of containers defined in a
Compose file.
```
docker-compose logs myservice
```
 Output: Logs of the specified service in the Compose file
 Explanation: This command retrieves and displays the logs of the
specified service ("myservice") defined in a Docker Compose file.
23. **docker-compose build**: Build images defined in a Compose
file.
```
docker-compose build
```
 Output: Image build process output
 Explanation: This command builds the Docker images defined in a
Docker Compose file, based on the corresponding build configurations.
24. **docker inspect**: Display detailed information about a
container or image.
```
docker inspect mycontainer
```
 Output: Detailed information about the container in JSON format
 Explanation: This command provides in-depth information about the
specified container, including its configuration, network settings, and
more.
25. **docker cp**: Copy files/folders between a container and the
host.
```
docker cp myfile.txt mycontainer:/path/to/destination
```
 Output: None
 Explanation: This command copies the specified file ("myfile.txt")
from the host to the specified container ("mycontainer") at the given
destination path.
26. **docker top**: Display the running processes of a container.
```
docker top mycontainer
```
 Output: List of running processes in the container
 Explanation: This command shows the running processes within the
specified container, including
the process ID (PID), user, CPU usage, and more.
27. **docker start**: Start a stopped container.
```
docker start mycontainer
```
 Output: None
 Explanation: This command starts the specified stopped container
("mycontainer").
28. **docker restart**: Restart a running container.
```
docker restart mycontainer
```
 Output: None
 Explanation: This command restarts the specified running container
("mycontainer").
29. **docker pause**: Pause a running container.
```
docker pause mycontainer
```
 Output: None
 Explanation: This command pauses the execution of processes within
the specified container ("mycontainer").
30. **docker unpause**: Unpause a paused container.
```
docker unpause mycontainer
```
 Output: None
 Explanation: This command resumes the execution of processes within
the specified paused container ("mycontainer").
31. **docker kill**: Send a signal to stop a container.
```
docker kill mycontainer
```
 Output: None
 Explanation: This command sends a termination signal to the specified
container ("mycontainer"), causing it to stop immediately.
32. **docker rename**: Rename a container.
```
docker rename mycontainer newname
```
 Output: None
 Explanation: This command renames the specified container from
"mycontainer" to "newname."
33. **docker stats**: Display real-time resource usage of containers.
```
docker stats
```
 Output: Real-time statistics of resource usage for all running containers
 Explanation: This command continuously displays live resource usage
statistics (CPU, memory, network I/O, etc.) for all running containers.
34. **docker attach**: Attach to a running container.
```
docker attach mycontainer
```
 Output: Console output of the attached container
 Explanation: This command attaches to the specified running container
("mycontainer") and displays its console output in the terminal.
35. **docker commit**: Create a new image from a container's
changes.
```
docker commit mycontainer myimage:v2.0
```
 Output: New image ID (e.g., "a1b2c3d4e5f6")
 Explanation: This command creates a new Docker image from the
changes made to the specified container ("mycontainer") and assigns it the
name "myimage" with the tag "v2.0."
36. **docker login**: Log in to a Docker registry.
```
docker login myregistry.com
```
 Output: Login successful message
 Explanation: This command logs in to the specified Docker registry
("myregistry.com") using the credentials provided by the user.
37. **docker logout**: Log out from a Docker registry.
```
docker logout myregistry.com
```
 Output: Logout successful message
 Explanation: This command logs out from the specified Docker registry
("myregistry.com") and clears the authentication credentials.
38. **docker history**: Show the history of an image.
```
docker history myimage
```
 Output: Image history, showing layers and their details
 Explanation: This command displays the history of the specified
Docker image ("myimage"), including each layer's commands and sizes.
39. **docker events**: Get real-time events from the server.
```
docker events
```
 Output: Real-time events occurring on the Docker server
 Explanation: This command continuously streams real-time events
from the Docker server, providing information about container and image
events, such as create, start, stop, etc.
40. **docker pause**: Pause all processes within a container.
```
docker pause mycontainer
```
 Output: None
 Explanation
: This command pauses all processes running inside the specified container
("mycontainer"), effectively freezing its execution.
41. **docker unpause**: Unpause all processes within a container.
```
docker unpause mycontainer
```
 Output: None
 Explanation: This command resumes the execution of all processes
within the specified paused container ("mycontainer").
42. **docker save**: Save an image to a tar archive.
```
docker save -o myimage.tar myimage
```
 Output: Tar archive file "myimage.tar"
 Explanation: This command saves the specified Docker image
("myimage") to a tar archive file named "myimage.tar."
43. **docker load**: Load an image from a tar archive.
```
docker load -i myimage.tar
```
 Output: None
 Explanation: This command loads a Docker image from the specified
tar archive file ("myimage.tar") and makes it available on the local Docker
host.
44. **docker import**: Import an image from a tar archive.
```
docker import myimage.tar myimage
```
 Output: Image ID of the imported image (e.g., "a1b2c3d4e5f6")
 Explanation: This command imports a Docker image from the specified
tar archive file ("myimage.tar") and assigns it the name "myimage."
45. **docker export**: Export a container's filesystem as a tar
archive.
```
docker export mycontainer > mycontainer.tar
```
 Output: Tar archive file "mycontainer.tar"
 Explanation: This command exports the filesystem of the specified
container ("mycontainer") as a tar archive file named "mycontainer.tar."
46. **docker import**: Import a previously exported container as a
new image.
```
docker import mycontainer.tar myimage
```
 Output: Image ID of the imported image (e.g., "a1b2c3d4e5f6")
 Explanation: This command imports a previously exported container
(as a tar archive) and creates a new Docker image with the name
"myimage."
47. **docker system df**: Show Docker disk usage.
```
docker system df
```
 Output: Disk usage summary of Docker resources
 Explanation: This command displays a summary of Docker's disk
usage, including the total size, used space, and available space for
containers, images, volumes, and more.
48. **docker system prune**: Remove unused data (containers,
images, networks, volumes, etc.).
```
docker system prune
```
 Output: Confirmation message for the deletion of unused data
 Explanation: This command removes unused Docker resources such as
stopped containers, unused images, networks not used by any container,
and dangling volumes.
49. **docker version**: Show the Docker version information.
```
docker version
```
 Output: Docker version details (Client and Server)
 Explanation: This command displays the version information of the
Docker client and server.
50. **docker info**: Show system-wide Docker information.
```
docker info
```
 Output: System-wide Docker information (e.g., Containers, Images,
Storage Driver, etc.)
 Explanation: This command provides detailed information about the
Docker installation and configuration on the host system, including the
number of containers, images, storage driver used, etc.
