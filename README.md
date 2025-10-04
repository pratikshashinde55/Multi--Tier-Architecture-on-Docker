# Multi--Tier-Architecture-on-Docker
#Creating a Blogging Site Using Docker (Manual Setup)
Environment Setup

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
