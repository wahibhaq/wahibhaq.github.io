---
layout: page
title: Presentations and Talks
---

### Battery Optimization Restrictions meets Notifications

*Date: 07.05.2019, Event: [Google I/O Extended Meetup](https://www.meetup.com/GDG-Munich-Android/events/260535959/)*

This was meant to share my personal hassle while dealing with restrictions enforced by Doze mode and App Standby buckets in the context of Notifications. Since 6.0, Android is trying to introduce more restrictions to make battery saving more efficient for its users but sometimes it can make life a bit difficult for developers. Important thing is to be aware of how Doze and Standby works and what we can do about it. We can either embrace it or try to fight it.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">2nd last talk at our <a href="https://twitter.com/hashtag/io19extended?src=hash&amp;ref_src=twsrc%5Etfw">#io19extended</a> event in munich Was <a href="https://twitter.com/wahibhaq?ref_src=twsrc%5Etfw">@wahibhaq</a> talking about doze mode and notification <a href="https://t.co/lex81TPNBc">pic.twitter.com/lex81TPNBc</a></p>&mdash; Benjamin Stürmer (@BenjaminStrmer) <a href="https://twitter.com/BenjaminStrmer/status/1125874581292691456?ref_src=twsrc%5Etfw">May 7, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#### Slides

<script async class="speakerdeck-embed" data-id="ddc64f16a3e84232af6e519a4ea635ec" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

---

### Kotlin Coroutines: How to continue work even when children tasks fail or timeout

*Date: 28.01.2019, Event: [KTUG Munich Jan Meetup](https://www.meetup.com/Kotlin-User-Group-Munich/events/257927489/)*

This talk was about sharing our learnings with the community while using Kotlin Coroutines for an interesting use case we had in our project. We are barely scratching the surface but I felt it might help others in making some better decisions with parent-child setup if they know the different uses of certain CoroutineScopes. 

#### Recording of the Talk

<blockquote class="twitter-tweet" data-lang="en"><p lang="in" dir="ltr">KTUG Jan Meetup - Wahib (Koroutines) <a href="https://t.co/XBImOxNQbf">https://t.co/XBImOxNQbf</a></p>&mdash; KTUG Munich (@KTUGMunich) <a href="https://twitter.com/KTUGMunich/status/1089953855700226050?ref_src=twsrc%5Etfw">January 28, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#### Slides

<script async class="speakerdeck-embed" data-id="57153cc20afc4883b10df98e95f42007" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

---

### Developers + Empathy for Users = Win-Win

*Date: 10.11.2018, Event: [DACHFest Munich](https://dachfest.com/)*

This lightning talk was given at DACHFest to highlight some misconceptions, why it matters to practice empathy towards users, adjusting expectations, working with designers and some tips from personal experiences.

<iframe width="560" height="315" src="https://www.youtube.com/embed/C1dGglWnxF4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


<script async class="speakerdeck-embed" data-id="27acd748e48e45cfae8214b0ea634b73" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

---

### Kotlin, What the Hype?

*Date: 26.10.2018, Event: KI University, Location: KI labs, Munich*

This talk was given as part of our regular bi-weekly "KI University" session which is an internal company event. It was meant to help other engineers getting familiar with the idea of "Kotlin" and motivate them to see its potential which goes beyond Android.

<script async class="speakerdeck-embed" data-id="dcb3a30f07c5409ca21fa773445e7f6b" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

---

### Monitoring GPS and Location Permission checks using LiveData

*Date: 08.08.2018, Event: [Android BBQ Munich](https://www.meetup.com/GDG-Munich-Android/events/251431459/)*

In our last project, we had to implement checks to ensure GPS is enabled on the device and Location Permission is granted by the user. It is important to highlight that both are critically needed to ensure the app can perform Location Tracking in background. Our best bet was to inform visually when the app is in the foreground or background in order to encourage the user to fulfill one or both of these requirements. This was only possible when UI (Activity/Fragment) and Service can listen to changes in GPS and Runtime Permission and react accordingly.

I faced several challenges while doing that and decided to solve it using LiveData. 

<script async class="speakerdeck-embed" data-id="0c5bc59951394469abb1137c349415ff" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>


---

### Future of Work in an AI Economy

*Date: 28.07.2018, Event: [Lightning Talks Munich](https://www.facebook.com/events/1982521875115551/), Location: Munich*

Today, the idea that “every company needs to become a software company” is considered almost a cliché. AI and Automation has solved a lot of our problems but we just can't ignore how it'll change employment forever. McKinsey in their 2017 report projected that up to 800 million workers could be displaced globally and as many as 375 million may need to learn new skills for new occupational categories. This talk was meant to create awareness about this topic, highlight misconceptions and share some recommendations on what we can do on individual level to adapt.

[![](http://img.youtube.com/vi/blIvBBv8DQY/0.jpg)](http://www.youtube.com/watch?v=blIvBBv8DQY "Future of Work in AI Economy")


<script async class="speakerdeck-embed" data-id="f819ae07935a475c82c3f71d578e9e12" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

--- 

## Hack your way to create a Website/Blog using Github Pages and Jekyll

*Date: 07.06.2018, Event: KI University, Location: KI labs, Munich*

How developers can use Github Pages and Jekyll to bring their personal, organisation or project websites up and running without any cost.

<script async class="speakerdeck-embed" data-id="764807e89b8a4c19862ff4e1453e7070" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

---

## Keynote talk: What all these years of Android Development have taught me the hard way

*Date: 31.03.2018, Event: [AndroidDevFest](https://www.facebook.com/events/2028371470710712/), Location: Islamabad, Pakistan*

This is just my humble effort to share insights and learnings from my career and things I wish I would have known back in the day. There will be advice, rant, anecdotes, things which worked for me and how devs can step up their game.

<script async class="speakerdeck-embed" data-id="68a88f909e684780911573531866dea0" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

--- 

## Introducing Google Design Sprint

*Date: 17.02.2018, Location: Munich, Germany*

This presentation was prepared for a meetup session hosted by [MindLinks](http://www.mindlinks.de/) to inform audience about "Google Design Sprint" and how everyone can use it for their projects. This community in Munich provides a creative space to young professionals and refugees with a shared interest in academic discussions.

<script async class="speakerdeck-embed" data-id="b13b5fb5ca704e12b461500057b88ab0" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

