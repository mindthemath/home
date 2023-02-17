---
title: "Architecture-Aware Docker"
date: 2022-09-12
# weight: 1
aliases: ["/arch-aware-docker"]
categories:
  - containerization
tags:
  - architecture
  - docker
  - devops
  - cloud
  - microservices
author: ["Michael Pilosov, PhD"]
showToc: true
TocOpen: true
draft: false
hidemeta: false
description: "Building Docker Images that Can Run on Any Architecture: A Guide for Developers"
ShowReadingTime: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

## Motivations
Docker images are a popular way of packaging and distributing software.
With the rise of different computing platforms and architectures, it has become increasingly important to be architecture-aware when creating and distributing images.
One way to achieve this is by building images that are compatible with multiple platforms, which can be accomplished using multi-arch images.

## Computer Architecture
In order to build architecture-aware Docker images that can run on different types of machines, it is important to have a basic understanding of computer architecture. Specifically, it is helpful to know about the instruction set architecture (ISA) used by the different processors that you are targeting, as well as any operating system requirements. 

### Instruction Sets
Instruction sets are the collection of instructions that a processor is capable of executing. Each instruction in the set is encoded as a unique sequence of bits and is capable of performing a specific operation, such as addition, multiplication, or comparison. Different processors have different instruction sets, and each instruction set has its own set of operations that can be performed. Understanding instruction sets is important for computer architecture, as it enables one to understand the capabilities and limitations of a processor and how it can be used to perform different types of computations.

For example, if you are building images that will run on both x86-64 and ARM processors, you will need to be aware of the differences in their respective ISAs and any specific optimizations or limitations of each. Additionally, you may need to take into account the endianness of the processors, as this can affect how data is stored and retrieved.

### IoT

On a practical note: multi-architecture Docker images are very helpful for IoT devices. Since IoT devices come in different architectures, having multi-architecture images will allow the same application to run on all the different architectures. It reduces the burden of having to create different images for each architecture and also speeds up the development process, allowing developers to focus on other aspects of their application. 

By using multi-architecture Docker images, IoT devices will be able to run the same application, regardless of the architecture of the device, reducing the maintenance burden of having to create separate applications for each device.


## What are Multi-Arch Images?
A multi-arch (multiple architecture) image contains multiple platform-specific layers, each of which is optimized for a specific hardware architecture.
By using the same tag for each platform-specific layer, you can ensure that users will always pull the correct layer for their architecture.

This approach is especially useful when working with teams of developers and users who are using different hardware architectures, as it simplifies the deployment process and ensures that everyone is running the same version of the software.

## Building Multi-Arch Images
To start building multi-arch Docker images, it's necessary to have an understanding of how CPU architectures work and how the Docker platform supports this functionality. Essentially, Docker allows for the building of a single image that can run on multiple platforms, which enables cross-platform development and deployment. 

To accomplish this, one needs to use the manifest command to create and manage manifests, which allow for the specification of different images for different platforms. An example of this would be specifying linux/amd64 and linux/arm/v7 images for an application to support different types of devices.


### docker buildx
Here's an example of how to tag and build a manifest for a Docker image:

```bash
docker buildx build --platform linux/amd64,linux/arm64 -t myimage:latest .
docker manifest create myimage:latest myimage:latest-amd64 myimage:latest-arm64
docker manifest push myimage:latest
```

This example uses the buildx command to build an image for two platforms (linux/amd64 and linux/arm64) and tag it as myimage:latest. The manifest create command then creates a manifest list that maps the myimage:latest tag to the two platform-specific images that were just built. Finally, the manifest push command pushes the manifest list to Docker Hub (or another container registry).

### Combining Images from Different Machines

If you're not using buildx, you can still build images for different architectures by using separate Dockerfiles for each architecture, and then building and tagging each image separately.

For example, you might have two separate Dockerfiles - one for x86 architecture and one for ARM architecture - and you would build and tag each one separately using the appropriate tag for each architecture. Once you've built the images for each architecture, you can then use the docker manifest command to create a multi-arch manifest for the images, which can then be pushed to a registry and used to automatically pull the correct image for the architecture on which it's being run.


Here's an example of how to build multi-arch Docker images on separate machines:

On machine 1 (x86 architecture), build and tag the image for the x86 architecture:

```bash
docker build -t myimage:latest-x86 .
```

On machine 2 (ARM architecture), build and tag the image for the ARM architecture:

```bash
docker build -t myimage:latest-arm64 .
```

Push the images to a container registry from their respective machines:
```bash
docker push myimage:latest-x86
```

```bash
docker push myimage:latest-arm64
```

From one of the two machines, pull the other image, then combine them like this into a manifest:

```bash
docker manifest create myimage:latest myimage:latest-x86 myimage:latest-arm64
```

Annotate the manifest to indicate the supported architectures:

```bash
docker manifest annotate myimage:latest myimage:latest-arm64 --os linux --arch arm64 --variant v8
docker manifest annotate myimage:latest myimage:latest-x86 --os linux --arch amd64
```

Push the manifest to the container registry:

```bash
docker manifest push myimage:latest
```
