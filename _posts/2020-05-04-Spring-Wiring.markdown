---
title: "Solving Spring Wiring With Repositories"
layout: post
date: 2020-05-04 22:48
image: /assets/images/posts/good.jpg
headerImage: true
tag:
- java
- spring
- web
category: blog
author: djacales
description: How I Solve The NULL Repository issue after bad wiring on Srping.
---

Hector Daniel Jacales Rojas <hjacales@gmail.com>
	
para mí
# Spring Wire Process

Recently in my job I started working with the Java Spring Framework. ( A Web development framework). As for every new Technology you start to learn there is a learning curve to pass.

And in the process there are always some frustrating times when something that should work doesn't.

But this is part of the job as developer. And fortunaly there are plenty of resources as stack overflow, blogs, books etc...

One of these momenths I pass. Was because somthing is called Wiring. In the Spring Framework.

I share the issue and how I solved it. After some time of try and error Process and reading on some web articles.

## Issue

Spring has something called JPA and CRUD Repositories. Within Entitys (Java Objects) it can map SQL tables with Java Objects in our code.

Using the Repositories Within the main class is easy. But when its necessary to use many clases and packages. It may arraise some errors in the program.

Before explain the issue I have to mention that in Spring we have 3 resources (layers).
@Controllers : Handle Web Request and Response to clients
@Services : Where the program's logic is coding.
@Repositories : Responsible of the Database consulting Process.

The way we can comunicate this three components is as follow:

#### Repository:

```java
package main.models.repository;


import main.models.SaldoFake;
import org.springframework.data.repository.CrudRepository;


// This will be AUTO IMPLEMENTED by Spring into a Bean called userRepository
// CRUD refers Create, Read, Update, Delete

public interface SaldoFakeRepo extends CrudRepository<SaldoFake, Integer> {

}

```

#### Main Controller
```java

public class API {

    public String someMetod(){
        Parser parser = new Parser();
        parser.valida();
    }
}

```
#### Service

```java

public class Parser {

    @Wire
    SaldosFakeRepo repo;

    public void valida(){
        repo.findAll();
    }
}

```

There is when the @Whire notation help us. So I usted as follow in my three packages.

But when I use the findById() helper on my repository the repo object was null. Si it always fail yo find the Entity.

## Solution

I didnt know I had to Wire The Entire Flow of the programa. No just wiring Inside services.

Wire the Service inside de API class , main controller.

```java

public class API {

    @Autowired
    PlainParser parser;

    public String someMetod(){
        Parser parser = new Parser();
        parser.valida();
    }
}

```

Also add @Service notation to Parser class and wire the Repository.

```java

@Service
public class Parser {
    @Autowired
    SaldosFakeRepo repo;
}
```

It is necessary also to Wire the Service, Controller, Componen class. So the repo actually can Wire with the Spring definition of a Repository. 