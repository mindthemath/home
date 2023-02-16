---
title: "Securing Docker Containers: Best Practices and Common Pitfalls"
weight: 100
aliases: ["/docker-security"]
tags: ["docker", "security", "containers", "networking"]
categories: ["workshops", "devops"]
description: "Learn the best practices for securing Docker containers, including managing access control, creating secure networks, and properly configuring port exposure."
hidemeta: false
cover:
    image: "" # image path/url
    alt: "<alt text>" # alt text
    caption: "<caption text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
---


## Motivations

When deploying Docker containers, it's important to understand that by default, a container's network interface is only accessible by other containers running on the same host. This can be problematic if you need to expose a container's services to the outside world. To do this, you need to create a network bridge between the host and the container.

Once the network bridge is established, you'll then need to consider which ports you need to expose to the outside world. By default, a container's ports are not exposed to the host or external network. You can use the docker run command's -p flag to expose a container's ports to the host machine or to the public internet.

There are several best practices to consider when managing container networking and exposing ports to ensure that your containers are secure. It's important to cover these best practices during the workshop to ensure that participants understand how to safely manage container networking in their own environments.

## Common Pitfalls
For the Docker security workshop, there are several common pitfalls that participants will encounter, and we'll make sure to cover how to address them. 

First, one common issue is the use of outdated or vulnerable base images, which can lead to security vulnerabilities in the container.
We'll discuss how to choose secure base images and keep them updated.

Another pitfall is failing to isolate container environments from the host system or other containers on the same network, which can lead to unauthorized access or data breaches.
We'll cover how to use network isolation and container permissions to prevent these issues.

Finally, many users don't properly secure access to container registries or manage access to images, which can lead to malicious users gaining access to sensitive data.
We'll cover the use of authentication and authorization measures to properly secure container images and registries.

An sampling of topics that may be covered (tailored to audience interest):

- Failure to keep base images updated with security patches
- Failure to set up correct user permissions within the container
- Running processes as root within the container
- Exposing too many ports or exposing ports without proper configuration
- Improper volume or bind-mount configuration, leading to unwanted data exposure
- Using untrusted third-party images without verifying their source or contents
- Storing sensitive information, such as passwords or credentials, in the container
- Running unneeded services or processes within the container, which can provide additional attack vectors
- Failure to properly implement access controls and authentication for the container
- Lack of monitoring and logging within the container, making it difficult to identify and respond to security events

It's important to be aware of these potential pitfalls in order to maintain the security of Docker containers and the systems on which they run. In our workshop, we'll discuss these topics in detail and provide guidance on how to avoid these issues.

## Workshop Format
This workshop will cover a range of security considerations for Docker containers, including networking and port forwarding. Participants will learn how to secure their Docker containers and prevent potential security breaches. We will go through a number of practical exercises, where participants will have the opportunity to explore and understand the following topics:

- Overview of Docker networking concepts and how they work
- Differences between Docker's default bridge network and user-defined networks
- How to use docker network create to create and manage user-defined networks
- Exposing ports with Docker, including the -p and --expose options
- Docker port forwarding, including the -p and --publish options
- Best practices for securing Docker containers, networks, and images

The workshop will be structured to include a mix of lecture-style presentation and hands-on exercises to help participants gain practical experience with Docker security concepts.