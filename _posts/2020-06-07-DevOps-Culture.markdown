---
title: "How To Transition To A DevOps Architecture "
layout: post
date: 2020-06-07 22:48
image: /assets/images/posts/spongebob.jpg
headerImage: true
tag:
- DevOps
- Architecture
- Jenkins
category: blog
author: djacales
description: How I participated on the process of adopting a DevOps culture. And Tools Used.
---

Hector Daniel Jacales Rojas <hjacales@gmail.com>

# How To Transition To A DevOps Architecture 

#### Tools And  Challenges  Based On My Experience.

Recently at the current job I am in, due to the nature of a new project the company has started. The need of adopt a new culture and practices to produce code and enforce the quality revision process. 

In the last months the company has already include tools for make coding easier. Such as a intern gitlab server ( to share code and have a central repository of the projects and collaboration between al tech staff) . But there were not enough to satisfy the company need to produce new products faster.

So we decide to investigate and implement new actions, tools and mindsets to ensure we can have the right architecture to develop, test , deploy and  maintain the software from now on. All around an efficient communication between teams and members of a team. All of this in times of Quarantine because of COVID-19.

![stack](https://djaquels.github.io/assets/images/posts/stack.PNG)

The first thing was to define the datasource we will count on. That includes SQL and NON-SQL Databases. SQL for the main of the data and Mongo to still have flexibility for non typical data requirements. After that the next step was  to define a model of coding, testing, deploying and administrate the different web services and libraries the company is developing.

For that we can connect the actual gitlab server to a new Jenkins Server ( Jenkins is a CI/CD tool ) , that help us to deploy, test and communicate every changes has component on our backlog of microservices is made. Jenkins has a very good and easy to use Microsoft Teams plugin , so we can track all changes to a component.

The deployment is made using Docker as our main tool to compact all the elements a service needs. In the future is planned to adopt Kubernets to manage a large amount of containers and have a private Docker Hub Repo.

The testing layer is still in early phases, but we include an unitesting phase to all of the new projects has started. This with the help of standard tools as JUNIT 5 and Pytest . With this new way of working the circle of software development has evolve and has become faster. By deleting some manual task and autmaticing those tasks. Also improving the communication between programmers and permitting the Front End staff to focus on make great and functional designs for the final client.

The last benefit has been to have a faster integration process, tank much because now make a change on a element in the integration process is faster and practically al automatic. Thanks to the gitlab-jenkins-testing-docker connection.

Based on this experience my recommendation is to at least have one tool for automating each layer  on a DevOps architecture , not exactly the tools we adopt but similar ones. For example a version control system such gitlab or github, a communication tool as teams, slack, etc… A Continuous Integration and Deploying system in the market there are Jenkins and Circle CI options but not are the only.  If the use of microservices is needed, the use of containers is essential.  On the testing side we tried and had make some experiments with Selenide. 

Of course this has just started and there still a lot to learn for me and my teammates  in this new Microservices, DevOps way of working. But this is part of growing and we are learning a lot in the road. 


