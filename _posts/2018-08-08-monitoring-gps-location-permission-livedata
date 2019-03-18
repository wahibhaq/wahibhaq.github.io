---
layout: post
title:  Monitoring GPS and Location Permission checks using LiveData
tags: [android, gps, runtime permission, livedata, kotlin]  
share-img: http://thetechnocafe.com/wp-content/uploads/2018/03/live_data_android.png
published: true
---

This talk was given at [Android BBQ Meetup](https://www.meetup.com/GDG-Munich-Android/events/251431459/)

In our last project, we had to implement checks to ensure GPS is enabled on the device and Location Permission is granted by the user. It is important to highlight that both are critically needed to ensure the app can perform Location Tracking in background. Our best bet was to inform visually when the app is in the foreground or background in order to encourage the user to fulfill one or both of these requirements. This was only possible when UI (Activity/Fragment) and Service can listen to changes in GPS and Runtime Permission and react accordingly.

I faced several challenges while doing that and decided to solve it using LiveData. 


#### Slides

<script async class="speakerdeck-embed" data-id="0c5bc59951394469abb1137c349415ff" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

#### Articles

Later, I ended up publishing detailed articles ([Part 1](https://medium.com/@wahibhaq/monitoring-gps-and-location-permission-checks-livedata-part-1-278907344b77) and [Part 2](https://medium.com/ki-labs-engineering/monitoring-gps-and-location-permission-checks-livedata-part-2-d8822ab951a6)) along with the github repo. If you are looking for just a quick summary then you can read it [here](http://wahibhaq.com/blog/monitoring-gps-and-location-permission-checks-livedata/).
