# Kubernetes Basic Concepts
## Problem Before Containers

In traditional development environments, developers often faced a common issue:

“It works on my machine but not on another machine.”

For example:

* Code running successfully on Windows might not work on Linux.

* Different machines may have different libraries, dependencies, or configurations.

This created inconsistencies between development, testing, and production environments.

# Virtualization

To solve this problem, Virtual Machines (VMs) were introduced.

Virtualization allows multiple operating systems to run on a single physical machine using a hypervisor.

## Example Architecture
Physical Machine
     |
Hypervisor
     |
VM1 (OS + App)
VM2 (OS + App)
VM3 (OS + App)

Each virtual machine contains:

* Its own operating system

* Required libraries

* Application code

## Problems with Virtual Machines

Although VMs solved many compatibility issues, they introduced new challenges:

* Heavy Images – VM images include the full operating system.

* Large File Size – Sharing VM images is difficult because they are very large.

* Slow Deployment – Starting a VM takes time.

* Difficult Scaling – Creating and scaling multiple VMs is slower and resource intensive.

Because of these limitations, a better solution was needed.

# Containerization

The next evolution was Containerization.

Containerization is also a form of virtualization, but it is much lighter.

Instead of including a full operating system, containers share the host machine’s kernel.

Container Architecture
Host Operating System
        |
   Container Runtime
        |
-------------------------
Container 1 (App + Dependencies)
Container 2 (App + Dependencies)
Container 3 (App + Dependencies)
## Key Idea

Containers remove the operating system layer inside the image and reuse the host OS kernel.

## Benefits of Containerization

* Lightweight

* Faster deployment

* Easy to share images

* Efficient scaling

* Consistent environment

## Container Images

In containerization, we create images.

A container image is a template that contains everything required to run an application.

It includes:

* Application code

* Runtime environment

* Required libraries

* System tools

* Configuration files

Once an image is created, it can run as a container.

The biggest advantage is:

If an image runs successfully on one machine, it will run exactly the same on any other machine.

## Challenges of Managing Containers

Although containers are lightweight and efficient, managing them manually becomes difficult when the number of containers increases.

Common container operations include:

* Running containers

* Monitoring containers

* Starting containers

* Restarting containers

* Destroying containers

* Performing health checks

* Scaling containers

Managing these tasks manually is not practical in large systems.

# Container Orchestration

To solve this problem, Container Orchestration was introduced.

Container orchestration automates the management of containers.

## Container Orchestration Handles

* Deployment of containers

* Container scaling

* Load balancing

* Networking

* Monitoring

* Self-healing (restarting failed containers)

A container orchestration platform enables organizations to efficiently manage containerized applications at scale.

However, performing container orchestration manually is extremely complex.

Therefore, automation tools were created.

# Google's Solution: Borg

Google developed an internal container orchestration system called Borg.

Borg was used inside Google to automatically manage containers.

It handled tasks such as:

* Scaling containers

* Restarting failed containers

* Scheduling workloads

* Managing infrastructure

However, Borg was an internal Google system and was not available to the public.

# Birth of Kubernetes

Inspired by Borg, Google created a new open-source project called Kubernetes.

Important points:

* Kubernetes is inspired by Borg

* It is not the same code as Borg

* It was written from scratch

Google released Kubernetes as an open-source project so that organizations worldwide could benefit from container orchestration.

# Kubernetes and CNCF

In 2014, Google donated Kubernetes to the Cloud Native Computing Foundation (CNCF).

Now:

* CNCF maintains Kubernetes

* Kubernetes is open source

* Anyone can use it free of cost

* The source code is available on GitHub

# Summary

The evolution of application deployment looks like this:

Traditional Deployment
        ↓
Virtual Machines
        ↓
Containerization
        ↓
Container Orchestration
        ↓
Kubernetes

Kubernetes solves the problem of automating container orchestration, making it easier to deploy and manage containerized applications at scale.
