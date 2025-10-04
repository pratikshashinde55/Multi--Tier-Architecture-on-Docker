# Multi--Tier-Architecture-on-Docker
# Creating a Blogging Site Using Docker (Manual Setup)
Environment Setup:

Platform: AWS EC2 Instance

Operating System: Amazon Linux (Amazon Linux 2)

## Three-Tier Architecture Overview
I will deploy a blogging platform using a three-tier architecture approach:

## [1]Application Tier (WordPress)

The front-end and core application logic will be handled by WordPress, running in a Docker container.

## [2]Database Tier (MySQL)

WordPress will connect to a MySQL container for data storage and retrieval.

## [3]Network Tier (Custom Docker Network)

A custom user-defined Docker network will be created to enable secure and seamless communication between the WordPress and MySQL containers.

# Step: 1 [Install Docker & Start Docker Services]
### [1]Launch EC2 instance and install docker inside EC2 and start docker Service:

<img width="1863" height="757" alt="Screenshot 2025-06-07 231058" src="https://github.com/user-attachments/assets/099da233-9182-47ce-a339-b81ce21475ce" />


    Docker install command:

    yum install docker -y 
    systemctl start docker

    <img width="1801" height="325" alt="Screenshot 2025-06-07 221621" src="https://github.com/user-attachments/assets/ac626acc-a78e-476e-99f1-389ca72bbb79" />

### [2]Start Docker Service command:

     systemctl enable  docker --now 
### [3]Check Docker Status:

      systemctl status docker

# Step: 2 [Launch MySQL Container using own Network]
Create database with own driver (database- container name)

Launch MySQL container using custom networks & adding environmental variables & Attach Host folder(Mount volume) Default folder of MySQL storage is /var/lib/mysql:

docker run -dit --name database --network psnet -v /mydata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=pratik55  -e MYSQL_DATABASE=mydatabase  -e MYSQL_USER=jack  -e MYSQL_PASSWORD=jack11 mysql
Inspect command for check:(here we see our Subnet range(10.0.0.1/16) to our given database container)

docker inspect database   
