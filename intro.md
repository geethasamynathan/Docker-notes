![alt text]({EC5934C4-13A7-4C0E-B617-997428DF05B5}.png)

![alt text]({4490D50C-51C0-4D65-8D58-23940C5CC14B}.png)


![alt text]({35423CDB-60E7-45D8-9CC9-272DE5B1A0E2}.png)


![alt text]({43814314-392D-4281-8564-E1E01F74D684}.png)

![alt text]({F51B53B3-D2B7-4AC4-9293-C5F7F359DDED}.png)

![alt text]({67FF8C6B-62A2-472B-A641-F0CCAA7484D6}.png)

![alt text]({B46C687E-166C-40CB-BFE8-F71E1E9515D7}.png)

hub.docker.com

# applcation development before Container

![alt text]({66E2B00C-DBF0-441E-B85B-D5EF31D62041}.png)
![alt text]({7358CFE6-1ECB-4EBD-BAA3-36E45E57E0C8}.png)
![alt text]({68A043E4-DC5C-4783-BC91-B6AA5EE13D35}.png)
![alt text]({DB4C9A50-DDFE-4EFF-8494-FC94B4AD50C7}.png)
![alt text]({047956AB-3AC8-48E4-9FD3-E6E9AB289066}.png)
![alt text]({6384744D-CD26-49EF-A105-437E40A8C315}.png)

![alt text]({1518DBC1-8D31-43DB-BD56-F7BF5BEC113C}.png)

![alt text]({34BDA4FF-FA5D-4460-B158-41B6F0F03192}.png)

# What is an Image? what is container?
![alt text]({65393367-B390-4C8B-BFB7-A16E5202F652}.png)

![alt text]({E0FCD968-BC4E-4DF3-A6FD-2256F66B71E8}.png)

![alt text]({04FFE7E3-9853-4F80-A513-5E97778B7F9E}.png)


# What is the Difference b/w Docker and VM?
![alt text]({7CD4BA48-9F34-40C2-A5F1-0DDB11E2AFCA}.png)
![alt text]({C50FB127-7EC8-4802-BA4F-9625D5BA82F0}.png)
![alt text]({E52C163B-7F99-486A-A2AA-7C30744CC0FB}.png)
![alt text]({D19C5721-EEA7-45B1-A9D5-47A5B3A43CD2}.png)
![alt text]({87ED23FF-A3A4-4C1A-BA1F-A9C08C26F6DA}.png)

![alt text]({361CFF7A-BE74-405C-BDF8-961B7559F567}.png)

# Docker Installation

![alt text]({8D3D2CC3-F0C5-4ED2-A1B2-002E801E4729}.png)

![alt text]({3372D687-CC67-4FA8-8E6A-91903368F2EB}.png)

# What is Docker Toolbox? when its need?

![alt text]({A0E75EDE-7271-4361-8063-E66EB2A7DA6B}.png)

# How do I run a container?


https://github.com/docker/welcome-to-docker



# Steps to install Microsoft SQl Server

https://hub.docker.com/r/microsoft/mssql-server

open command prompt
`docker pull mcr.microsoft.com/mssql/server`

![alt text]({B5C14F00-385F-4835-9965-B3261A4CFFB8}.png)


to know the running instances in docker 
`docker ps`

![alt text]({49DA594C-58C0-46DB-AC77-8A003928C717}.png)
to run the ssms from docker

`docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrong(!)Password" -e "MSSQL_PID=Evaluation" -p 1433:1433  --name sqlpreview --hostname sqlpreview -d mcr.microsoft.com/mssql/server:2022-preview-ubuntu-22.04`


https://hub.docker.com/r/microsoft/mssql-server


# run ssms from vs code
terminal
`docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=Password@123" -e "MSSQL_PID=Evaluation" -p 1433:1433  --name sqlpreview --hostname sqlpreview -d mcr.microsoft.com/mssql/server:2022-preview-ubuntu-22.04`

open ssms &rarr; database engine localhost,1433

![alt text]({A6AE4277-04BF-4FDE-89EA-97D50307C360}.png)

create db (demo_db).

![alt text]({A6AE4277-04BF-4FDE-89EA-97D50307C360}-1.png)


# to connect with ssms from vs terminal
docker exec -it cefc2b48779d /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'yourStrong(!)Password'

1) select name from sys.sysdatabases
2> go

![alt text]({E4FA78BE-5866-4D1A-A2A0-F619376370DF}.png)


# What is container in docker?
A container in Docker is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. Think of it as a portable unit that can be deployed consistently across various environments, such as development, testing, and production, without worrying about the underlying infrastructure.

# Key Features of Docker Containers
**Isolation:** Containers run in isolation from each other, ensuring that the applications inside them do not interfere with one another.

**Consistency:** Containers ensure that applications run the same, regardless of where they are deployed.

**Efficiency:** Containers share the host system's kernel, making them more lightweight and efficient compared to virtual machines.

**Portability:** You can build a container on one system and run it on any other system that supports Docker, making it easy to move applications across different environments.

# Example of Running a Simple Container
To give you a practical sense, here's an example of how you can run a simple container using Docker:

**Pull an Image:** First, you need to pull a Docker image from Docker Hub. For instance, to pull the latest Nginx image, you would run:


`docker pull nginx:latest`
**Run the Container:** Once you have the image, you can run it as a container:


`docker run --name mynginx -d -p 80:80 nginx:latest`
This command starts a new container named mynginx from the Nginx image, runs it in detached mode (-d), and maps port 80 of the host to port 80 of the container.

# Commands Overview
docker pull <image>: Downloads a Docker image from Docker Hub.

docker run <options> <image>: Starts a new container from a Docker image.

docker ps: Lists all running containers.

docker stop <container>: Stops a running container.

docker rm <container>: Removes a stopped container.

Containers are incredibly useful for creating a consistent development environment, scaling applications, and simplifying deployment processes.