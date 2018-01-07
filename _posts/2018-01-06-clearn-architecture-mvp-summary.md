---
layout: post
title: A Brief Summary of thoughts on Clean Architecture and MVP
tags: [clean architecture, model view presenter, mvp, architecture, mobile, android]  
fb-img: http://wahibhaq.github.io/img/blog/posts/summary-thoughts-clean-architecture-mvp/clean-architecture-ring-diagram.png
published: true
---

<br>
Roughly 3 months ago I was going through the job search phase for Android dev position and went through all kinds of different interviews. From one of the potential employers, I was given a challenge to submit a 1 page recommendation of an architecture for a situation as follow:

> You are an experienced developer. Can you design 1-page architecture of an app for a financial product with 50k users base (3k daily), that can work in a modern setup of development, e.g. Spotify squads? Once you come onboard you may have to design for 10-100x userbase. The architecture can be a generic view. 

<br>
<img src="http://wahibhaq.github.io/img/blog/posts/summary-thoughts-clean-architecture-mvp/architecture-meme.jpg" width="450" height="400" align="center">
<br><br>
I did some research, compiled my personal thoughts and submitted it. Kindly don't expect to find details of Clean Architecture or MVP in this post as it was supposed to be something which just gives an idea about the proposed solution and highlight my reasoning behind it. Ignoring what happened with the interview process, I thought to publish them as a blog post now. 

Something unrelated but 2017 was the year when I got super interested in **[Clean Architecture](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164/ref=sr_1_1?ie=UTF8&qid=1515276671&sr=8-1&keywords=clean+architecture)** and was lucky to get hands-on experience with implementing **[MVP](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter)** in our Android source code at Freeletics. Architectures in general has always been my area of interest and more importantly because I was never able to properly use one in any of my past Android projects. Android Devs clearly know the struggle with building robust, production-quality and maintainable apps without any reliable app architecture. 

Interesting enough, 2017 will always be remembered as the year when for the first time Google officially recommended an app architecture for Android apps and called it  **[Architecture Components](https://developer.android.com/topic/libraries/architecture/index.html)**. It is basically a collection of libraries to provide a simple, flexible and practical approach that frees developers from some common problems so they can focus on writing modular apps with less boilerplate code and building great experiences.


--- 

<br>
### What should we expect from a modern app architecture? 

IMHO it needs to be robust, stable, easily extendable with as less effort as possible, adaptable to change as per agile requirements, fast to incorporate new platform features and, supports testability, at the same time, understandable to many different developers to ensure maintainability.

I believe *Clean Architecture* is the answer.

### Clean Architecture

<img src="http://wahibhaq.github.io/img/blog/posts/summary-thoughts-clean-architecture-mvp/clean-architecture-ring-diagram.png" width="400" height="300" align="center">

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Source: 8thlight.com

In [Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html), the code is separated into layers in an onion shape with one dependency rule: The inner layers should not know anything about the outer layers. Inner layers contain business logic, outer layers contain implementation and middle layer contain Interface Adapters. Each ring represent one layer of abstraction.


```
Some key technical benefits achieved:

> Abstraction over Implementation
> Single Responsibility Principle 
> Separation of Concern
> Decoupled Code
```
<br>
#### Different layers, components and how they communicate with each other

<img src="http://wahibhaq.github.io/img/blog/posts/summary-thoughts-clean-architecture-mvp/srp-clean-architecture-diagram.png" width="700" height="350" align="center">
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Source: five.agency

<br>
##### Presentation/UI Layer
<br>

* MVP is much suitable for the UI/presentation layer. 
* Views are dumb and implement [Passive View](https://martinfowler.com/eaaDev/PassiveScreen.html) pattern. It is a set of interfaces that could be implemented by any Android view, such as Activities, Fragments, Adapters or Custom Views.
* Presenter serve as a middleman between views (abstractions over Android specific components) and the business logic (interactors/Use Cases). They handle user interactions, invoke appropriate business logic, and send the data to the UI for rendering.
* Presenter doesn’t depend on Android classes hence improves testability.

<br>
##### Domain Layer
<br>

* Use Case is something like “Transfer money from one account to another”. Each Use Case is a reusable component that executes a specific business logic. It fetches the data from a repository, executes the business logic and returns the result to the presenter. 

<br>
##### Data Layer (Database & API)
<br>

* [Repository Pattern](https://martinfowler.com/eaaCatalog/repository.html) is responsible to create an abstraction of the data sources from which the Use Cases get the data to act upon. All under-the-hood persistence should be here: DAOs, ORM stuff, Retrofit (or any other Network related stuff) services, JSON parsing etc.
* App should work seamlessly even on a spotty network. The ability to cache and reuse previously fetched resources is a critical aspect of optimizing for performance.
* Business logic shouldn’t know where the data comes from. Act locally, but sync globally.

<br>
##### Device Layer
<br>

* Device contains the implementations of the gritty Android stuff such as sensors, alarms, notifications, players, all kinds of Managers, and so on. 

<br>
### Analysis of Proposed Architecture
<br>

* Adheres to Clean Architecture.
* It’s all neatly separated by module level, package level, and class level. So *Single Responsibility Principle* and *Separation of Concern* should be satisfied. 
* Business logic doesn’t touch the Android directly anymore and this should result in a decoupled codebase.
* We’ll have nicely separated classes and by injecting mock implementations of respective dependencies can make testing much easier.
* No compulsion to use Presenters to handle presentation logic, we could say that Clean architecture is “frontend” agnostic – meaning we can use MVP, MVVM or anything else on top of it. 
* The Presenter depends on the View interface and not directly on the Activity: in this way, we succeed in decoupling the presenter from the view implementation respecting the D of the [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) principles. We can replace the concrete view without changing a line of code of the presenter. Furthermore, we can easily unit-test presenter by creating a mock view.
* Every layer to have its own model that it works with, so the concrete details, such as views, do not depend on the specific details of the lower layer implementations.
* Instead of using callbacks to communicate between layers we can use the power of [RxJava](https://github.com/ReactiveX/RxJava) to provide the data upstream and let it handle thread scheduling for us. Each of the inner layers can transform the data in a way the outer layer can understand it.
* Allows changing the implementation of any outer layer without having to make a lot of changes in our codebase and fulfills the Extendability requirement.
* Following this approach is difficult and time consuming but consider it like doing a favor to future developers that are going to work and maintain the code.
* It is worth mentioning, that this supports using a dependency injection framework like [Dagger](https://google.github.io/dagger/). 

<br><br>
### Cross-Functional Team and Architecture
<br>

If you remember, Challenge description had a mention of **[Spotify Squads](https://labs.spotify.com/2014/03/27/spotify-engineering-culture-part-1/)** which is a very interesting concept coming out of Spotify Engineering Culture. Product squads seem to be a great way to build strong, knowledgeable development teams. In layman's terms, Squad is a small cross-functional self-organized scrum team. They have end-to-end responsibilities and they work together towards their long-term mission. On Squads the key drive is autonomy. 

For an employer, being Agile is a critical requirement and hence the expectation from an architecture to support it.  One of the more important agile principles is: 

> “The best architectures, requirements, and designs emerge from self-organizing teams.”


* [Benji Weber](http://benjiweber.co.uk/blog/2014/03/01/cross-functional-teams-vs-software-architects/) argues that there's no need of a person whose role is the Architect in a team. It is a responsibility of the team. In an ideal team, each member would be thinking about overlapping and complementary issues. 
* The software architecture shouldn't be complicated in order to make it difficult for a team of 5 to 9 members to take a feature from all the way to shippable. 
* Clean Architecture provides a separation of concerns that gives development teams the cadence and agility they need to manage the complexity and rapid change in their environment. By design it creates a clear cut between your components, and at the same time establishes the contract for future communication. This allows android devs to work in harmony with members of other *tribes*. 
* The practise of defining the [MVP contract](https://github.com/googlesamples/android-architecture/blob/todo-mvp-clean/todoapp/app/src/main/java/com/example/android/architecture/blueprints/todoapp/taskdetail/TaskDetailContract.java) before starting working on a feature indirectly helps android devs in the same *squad* to efficiently define areas of responsibilities among themselves. 
