---
title: "Deploying JupyterHub with Docker-Compose: A Workshop for Academic Teams"
# date: 2023-01-29T11:30:03+00:00
weight: 25
aliases: []
tags: ["jupyterhub", "docker-compose", "computational-reproducibility", "team-collaboration"]
categories: ["workshops"]
showToc: true
TocOpen: false
draft: false
math: false
hidemeta: false
comments: false
description: "Learn to deploy JupyterHub using docker-compose to improve computational reproducibility, facilitate team collaboration, and provide a flexible, OS-agnostic interface for research."
disableHLJS: false # to disable highlightjs
disableShare: false
ShareButtons: ["linkedin", "twitter", "reddit"]
hideSummary: true
searchHidden: false
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: false
cover:
    image: "" # image path/url
    alt: "<alt text>" # alt text
    caption: "<caption text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
editPost:
    URL: "https://github.com/mindthemath/home/tree/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---


## Introduction
JupyterHub is a multi-user version of Jupyter Notebook, an open-source web application for interactive computing and data science. By deploying JupyterHub with Docker Compose, teams and labs of academic researchers can benefit from its features, such as increased computational reproducibility, fast and easy onboarding of new team members, and an operating system agnostic interface.

*Note*: This workshop is primarily targeted at PI's and members of faculty/administration, but students are also welcome to attend (and perhaps become their group's "maintainer"). Students can learn to maintain their own research environments, which will improve their individual contributions, but the greatest increases in productivity will come from adoption at the lab (or research group) level.

## Advantages of using JupyterHub
By deploying JupyterHub with Docker Compose, academic researchers and teams can greatly benefit from its advantages, including increased computational reproducibility, fast onboarding of new members, and an operating system agnostic interface. The *ease* and *flexibility* of deploying JupyterHub with Docker Compose make it an ideal tool for collaborative research and data science.

- **Computational Reproducibility**: Docker containers allow for easy replication and distribution of research environments, ensuring that all team members are using the same software, libraries, and configurations.
- **Onboarding**: New team members can quickly begin research by avoiding all the computational set-up. They have a working environment from the first day to begin focusing on innovating, not managing dependencies.
- **OS Agnostic Interface**: By using JupyterHub through a web browser, the underlying operating system of team members' laptops or machines becomes less important. The laptop becomes a "thin-client", and all necessary tools are provided through the JupyterHub environment. Many different compute environments can be accessed through one consistent web-browser interface (to accomodate different lines of research inquiry).


## Workshop Overview

In this workshop, we will cover the process of deploying JupyterHub using Docker-Compose, including:

- An overview of JupyterHub and why it's beneficial to teams of academic researchers
- An introduction to Docker-Compose and why it's well-suited to deploying JupyterHub
- Steps for setting up and deploying a JupyterHub instance using Docker-Compose
- Discussion of best practices for managing and scaling JupyterHub deployments

## Learning Outcomes

By the end of this workshop, participants will:

- Understand the benefits of using JupyterHub for teams of academic researchers
- Have hands-on experience deploying JupyterHub using Docker-Compose
- Be equipped to manage and scale JupyterHub deployments in their own academic environments

## Workshop Structure

1. Introduction to JupyterHub
   - What is JupyterHub
   - Benefits of using JupyterHub for academic research teams
   - Key use cases for JupyterHub in a research environment
1. Using JupyterHub in a Team Setting
   - Sharing and collaborating on notebooks and other dat
   - Setting up a computational environment that is consistent across team members, using different configurations
   - Ensuring computational reproducibility and reproducible results
   - Getting new team members "spun up" quickly and efficiently
1. Introduction to Docker-Compose
    - What is Docker-Compose and how does it work
    - Benefits of using Docker-Compose for deploying JupyterHub
1. Setting up JupyterHub with Docker-Compose
    - Step-by-step guide to deploying a JupyterHub instance using Docker-Compose
    - Configuring JupyterHub with Docker Compose
    - Setting up the compute environment (what JupyterHub will leverage)
    - Discussion of available options and configurations
1. Advanced Topics in JupyterHub Deployment
   - Customizing the JupyterHub user interface
   - Managing user accounts with LDAP or OAuth vs HashAuth
   - Scaling JupyterHub to accommodate large numbers of users, how to assess your specific needs
   - Troubleshooting and maintenance of JupyterHub
1. Hands-on Practice and Discussion
    - Participants will follow along for the deployment of JupyterHub to which they'll be able to connect and interact
1. Conclusion and Next Steps
   - Recap of key takeaways from the workshop
   - Opportunities for further learning and exploration
   - Q&A session
