# Multi-Tier Java Web Application – Infrastructure Lab

A hands-on infrastructure project focused on designing and provisioning a multi-tier Java web application environment using **Vagrant, VirtualBox, and Linux virtual machines**.

The project explores how enterprise applications are separated into different infrastructure layers to improve scalability, maintainability, and service isolation.

> **Project status:** Initial infrastructure design and Vagrant configuration prepared. Application services and end-to-end integration are not yet deployed.

## Architecture Overview

The environment is designed around five dedicated Linux virtual machines, each responsible for a specific infrastructure component.

```text
                   Client / Web Browser
                           |
                           | HTTP Requests
                           v
                  +------------------+
                  |    WEB01         |
                  |    Nginx         |
                  | 192.168.56.11    |
                  +------------------+
                           |
                           | Reverse Proxy
                           v
                  +------------------+
                  |    APP01         |
                  | Java + Tomcat    |
                  | 192.168.56.12    |
                  +------------------+
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
        +----------+  +----------+  +----------+
        |  DB01    |  |  MC01    |  |  RMQ01   |
        |  MySQL   |  | Memcached|  | RabbitMQ |
        | .56.15   |  | .56.14   |  | .56.13   |
        +----------+  +----------+  +----------+
```

## Infrastructure Components

| Machine | Role | Operating System | IP Address | RAM |
|---|---|---|---|---:|
| web01 | Web Server – Nginx | Ubuntu 22.04 | 192.168.56.11 | 1 GB |
| app01 | Application Server – Tomcat | CentOS Stream 9 | 192.168.56.12 | 6 GB |
| rmq01 | Message Broker – RabbitMQ | CentOS Stream 9 | 192.168.56.13 | 1 GB |
| mc01 | Caching Server – Memcached | CentOS Stream 9 | 192.168.56.14 | 1 GB |
| db01 | Database Server – MySQL | CentOS Stream 9 | 192.168.56.15 | 2 GB |

## Technology Stack

**Infrastructure and Virtualization**
- Vagrant
- Oracle VirtualBox
- Linux (Ubuntu and CentOS Stream 9)

**Web and Application Layer**
- Nginx
- Apache Tomcat
- Java

**Data and Messaging Layer**
- MySQL
- Memcached
- RabbitMQ

**Development and Build Tools**
- Git
- Apache Maven

## Project Objectives

- Understand multi-tier application architecture.
- Provision multiple Linux virtual machines using Infrastructure as Code principles.
- Configure private networking and inter-server communication.
- Understand reverse proxy architecture using Nginx.
- Deploy Java applications using Apache Tomcat.
- Integrate relational databases, caching systems, and message brokers.
- Develop practical Linux system administration and infrastructure troubleshooting skills.

## Repository Structure

```text
multi-tier-java-app-vagrant/
│
├── Vagrantfile
├── README.md
└── .gitignore
```

## Getting Started

### Prerequisites

- Windows, Linux, or macOS host machine.
- Oracle VirtualBox.
- HashiCorp Vagrant.
- Sufficient RAM and disk space for the configured virtual machines.

### Verify Installation

```bash
vagrant --version
VBoxManage --version
```

### Initialize the Environment

Clone the repository:

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/multi-tier-java-app-vagrant.git
```

Navigate into the project:

```bash
cd multi-tier-java-app-vagrant
```

Validate the Vagrant configuration:

```bash
vagrant validate
```

Start the virtual machines:

```bash
vagrant up
```

Check machine status:

```bash
vagrant status
```

Connect to a specific machine:

```bash
vagrant ssh web01
```

Stop the machines:

```bash
vagrant halt
```

Destroy the Vagrant-managed machines:

```bash
vagrant destroy
```

**Note:** The full environment is configured to allocate approximately 11 GB of RAM, so adequate host resources are required.

## Infrastructure Deployment Strategy

The original design uses Vagrant and VirtualBox to provision an on-premises-style environment.

Due to local hardware limitations, the next implementation phase will explore deploying the same architecture on **Amazon Web Services (AWS)** using Terraform.

The AWS implementation will focus on:

- Infrastructure as Code with Terraform.
- AWS VPC and subnet design.
- EC2 provisioning.
- Security Groups and network isolation.
- Linux server configuration.
- Application deployment and integration.

## Learning Outcomes

This project is intended to demonstrate practical knowledge of:

- Multi-tier architecture.
- Linux administration.
- Virtualization and resource allocation.
- Infrastructure provisioning.
- Network configuration.
- Web and application server integration.
- Database and messaging infrastructure.
- Cloud infrastructure concepts.

---

**Author:** Mohamed Hassan

**Project:** Multi-Tier Java Web Application Infrastructure Lab
