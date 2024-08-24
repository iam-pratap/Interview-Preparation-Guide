`1. What is a container ?`

A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.
A container is a bundle of Application, Application libraries required to run your application and the minimum system dependencies.


`2. What is the Difference between Containers & Virtual Machines ?`

Containers and virtual machines are both technologies used to isolate applications and their dependencies, but they have some key differences:

**1. Resource Utilization:** Containers share the host operating system kernel, making them lighter and faster than VMs. VMs have a full-fledged OS and hypervisor, making them more resource-intensive.

**2. Portability:** Containers are designed to be portable and can run on any system with a compatible host operating system. VMs are less portable as they need a compatible hypervisor to run.

**3. Security:** VMs provide a higher level of security as each VM has its own operating system and can be isolated from the host and other VMs. Containers provide less isolation, as they share the host operating system.

**4. Management:** Managing containers is typically easier than managing VMs, as containers are designed to be lightweight and fast-moving.

![Screenshot 2023-02-07 at 7 18 10 PM](https://user-images.githubusercontent.com/43399466/217262726-7cabcb5b-074d-45cc-950e-84f7119e7162.png)

`3. Why are containers light weight ?`

Containers are lightweight because they use a technology called containerization, which allows them to share the host operating system's kernel and libraries, while still providing isolation for the application and its dependencies. This results in a smaller footprint compared to traditional virtual machines, as the containers do not need to include a full operating system. Additionally, Docker containers are designed to be minimal, only including what is necessary for the application to run, further reducing their size.


`4. What is Docker ?`

Docker is an open source containerization platform it enables developers to package the application into containers.


`5. What is Docker LifeCycle ?`

Users would create a Dockerfile with a set of instruction or commands that defines a docker image. For example, which base image to choose? what dependencies should be installed for the application to run ? etc..

Docker images act as a set of instructions to build a Docker container. It can be compared to a snapshot in a VM.

![Screenshot 2023-02-08 at 4 32 13 PM](https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png)

`6. What is the difference between docker COPY and docker ADD`

Docker ADD can copy the files from a URL unlike Docker COPY which can only copy files from host system into the container.

`7. What is the difference between CMD and ENTRYPOINT?`
**CMD:** Sets default parameters that can be overridden from the Docker Command Line Interface (CLI) when a container is running.
**ENTRYPOINT:** Default parameters that cannot be overridden when Docker Containers run with CLI parameters

`8. what are the networking types in Docker and what is the default?`

The default networking in Docker is Bridge
Howerver, you can change the default type and configure one of the
1. Bridge
2. Overlay
3. Host
4. MacVlan 

`9. What is a Multi-stage Build in Docker?`

Multi-stage build allows you to build your docker container in multiple stages allowing you to copy artifacts from previous stages for reducing the final image size.
Example of Dockerfile with multi-stage build:
```
FROM builder as build
# Build stage

FROM alpine
# Final stage
COPY --from=build /app /app
```

`10. What are distro less images in Docker?`

Distro-less images contain only your application and its runtime dependencies with a very minimum operating system libraries. They do not contain package managers, shells or any other programs you would expect to find in a standard Linux distribution.
They are very small and lightweight images.


`11. Real time Challenges with Docker?`

- Docker is a single daemon process. Which can cause a single point of failure, If the Docker daemon goes down for some reason all the application are down.
- Docker Daemon runs as a root user. Which is a security threat. Any process running as a root  can have adverse effects. when it is comprised for security reasons, it can impact other applications or containers on the host.
- **Resource Constraints:** If you're running too many containers on a single host, you may experience issues with resource constraints. This can result in slow performance or crashes.

`12. What steps would you take to secure containers?`

Some of the steps:
- Use Distro-less or images with not too many packages as your final image in multi stage build, so that there is less chance of CVE or security issues.
- Ensure that the networking is configured properly. This is one of the most common reasons for security issues. If required configure custom bridge networks and assign them ti isolate containers.
- Use utilities like Sync to scan your container images. 



