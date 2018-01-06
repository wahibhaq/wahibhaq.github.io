---
layout: post
title: A Brief Summary of thoughts on Clean Architecture and MVP
tags: [clean architecture, model-view-presenter, architecture, mobile, android]  
fb-img: http://wahibhaq.com/img/blog/posts/freeletics-android-tech-stack-2017/freeletics-app-view.png
published: false
---

# A Brief Summary of thoughts on Clean Architecture and MVP









Modern app architecture — it needs to be robust, stable, easily extendable with as less effort as possible, adaptable to change as per agile requirements, fast to incorporate new platform features and, supports testability, at the same time, understandable to many different developers to ensure maintainability.

#### Clean Architecture

<img src="http://wahibhaq.github.io/img/blog/posts/summary-thoughts-clean-architecture-mvp/clean-architecture-ring-diagram.png" width="350" height="250" align="center">

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Credits: 8thlight.com

In [Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html), the code is separated into layers in an onion shape with one dependency rule: The inner layers should not know anything about the outer layers. Inner layers contain business logic, outer layers contain implementation and middle layer contain Interface Adapters. Each ring represent one layer of abstraction.

```
> Abstraction over Implementation
> Single Responsibility Principle 
> Separation of Concern
> Decoupled
```

##### Different layers, components and how they communicate with each other




