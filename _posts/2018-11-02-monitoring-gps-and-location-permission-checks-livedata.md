
---
layout: post
title:  Monitoring GPS and Location Permission checks using LiveData
subtitle: Part 1 and Part 2
tags: [Android, LiveData, GPS, Runtime Permission, Kotlin]  
share-img: https://user-images.githubusercontent.com/273389/47611109-b13ac580-da5e-11e8-8464-930819aa476c.png
published: true
---

In our last project, we worked on a smartphone app to combat electric vehicle anxiety by understanding users’ needs, providing the owner with real-time data about their drives and offering a mechanism to compare suitable electric vehicles. In order to make that happen, tracking of driving behaviour through the app was an essential aspect of the project. It means that the app should be able to constantly listen to location coordinates in the background during the user’s journey while driving.

We had to implement checks to ensure **GPS** is enabled on the device and **Location Permission** is granted by the user. It is important to highlight that both are critically needed to ensure the app can perform Location Tracking during all drives.

### Use Case 🚙
> Imagine a scenario when the user installs the app, goes through onboarding and maybe grants Location Permission but ignores the dialog which prompts to enable GPS. Even worse, the user didn’t grant permission access or revoked later for any reason. Now it is safe to assume that user will even forget about the newly installed app and intended goal won’t be achieved.

### Updated Use Case 🚙
> Imagine a scenario when the user installs the app, goes through onboarding and grants Location Permission and enables GPS when prompted. There is still a chance that the user can revoke permission at any time in future for any reason. Even worse, the user started driving but don’t have GPS enabled. Those drives will never be tracked and the app will not be able to perform its intended goal.

Our best bet was to inform visually when the app is in the **foreground or background** in order to encourage the user to fulfil one or both of these requirements. This was only possible when UI (Activity/Fragment) and Service can listen to changes in GPS and Runtime Permission and react accordingly.

I faced several challenges while doing that and decided to share my learnings and solution. It is not the best solution ever but something which works for now and I would be more than happy and thankful to hear feedback on doing it in a better way ✌️

## Sample App UI

<br>

<img src="https://user-images.githubusercontent.com/273389/47611112-c152a500-da5e-11e8-85dd-73dbd1cd1e7c.png" width="150" height="350" align="left"> 

<img src="https://media.giphy.com/media/xWfplzYLnWSF3zivrm/giphy.gif" width="200" height="350" align="middle"> 

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
<img src="https://media.giphy.com/media/1ynT3NyWY0daNA8XEk/giphy.gif" width="200" height="350" align="middle">

### Implementation

Before I move to implementation part, I would like to mention that our team already decided to use [Architecture Components](https://developer.android.com/topic/libraries/architecture/) so it was a natural choice to opt for [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) to implement GPS and Permission Listeners so to say.

In the [first part](https://medium.com/@wahibhaq/monitoring-gps-and-location-permission-checks-livedata-part-1-278907344b77) of this tutorial, we can see how to implement checks using LiveData and observe on UI level.

In the [second part](https://medium.com/ki-labs-engineering/monitoring-gps-and-location-permission-checks-livedata-part-2-d8822ab951a6) of this tutorial, we can see how to implement checks using LiveData and observe on the background Service level.

---

You can have a look at the code on [GitHub](https://github.com/ki-labs/gps-permission-checks-livedata/).


