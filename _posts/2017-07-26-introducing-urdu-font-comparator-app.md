---
layout: post
title: How I ended up working on "Urdu Font Comparator" Project
tags: [android, urdu, font, pakistan, google play, open-source]  
fb-img: http://wahibhaq.github.io/img/projects/Urdu_Banner_Cover.png
published: true
---

<br>

> "If your life is not on a successful track, then ask yourself: Am I a consumer or a creator?"
 
It was a New Year's goal of mine to develop and publish my own Android app while contributing something to Pakistani 
community no matter how minor is the impact. It was supposed to be a side-project which I'll do in free time and 
get a chance to actually design UI, brainstorm about UX and also practice some newly learnt Android concepts. 
I collected couple of ideas back in Feb but one dawn article and one small problem lead me to this idea of building
a **[Urdu Font Comparator](https://play.google.com/store/apps/details?id=com.androidistan.urdufontcomparator)** application.

<br>

<img src="https://media.giphy.com/media/xUOrvYu2MF4xXWGimQ/giphy.gif" width="250" height="450" align="middle"> 

<br>

Those who know me are aware of my affinity with Urdu but like many of us I never took Urdu seriously until 
I moved to Germany. We don't write Urdu in our daily lives, ever! We do write Roman Urdu but that's not how 
it should be. I always wondered why people from every other nationality uses their native language to communicate 
and write messages except Pakistanis. We either use Roman Urdu or just plain English. This was just more troubling 
for me than embarrassing because no one cares about it anymore. I found my lost love and dignity once I started 
using Urdu in text messages last year.

<img src="https://i.imgur.com/9nw5ttS.png" width="500" height="200" align="middle">

Credits: [Rekhta](https://rekhta.org/couplets/saliiqe-se-havaaon-men-jo-khushbuu-ghol-sakte-hain-unknown-couplets?lang=ur)


[Dawn](https://www.dawn.com/news/1313737) published an article in Feb introducing [**Meher Nastaliq**](http://csalt.itu.edu.pk/urdufont/) 
font developed by ITU’s Center for Speech 
and Language Technologies ([CSaLT](http://csalt.itu.edu.pk/)) laboratory. Now, I was already aware that Urdu suffers big time
when it comes to it's adoption on Web and even worse when it comes to Mobile devices. We can't even claim it to be a language 
which has successfully integrated with what we know as "[Digital Age](https://en.wikipedia.org/wiki/Information_Age)" and 
one of the many reasons is lack of an optimal font. We have actually many Urdu fonts but still not something of an optimal 
size, quickly renderable, supports OTF and, more importantly, adheres to intricate Nastaliq style. I was so happy to know that and wanted to just try out the font right away and this is exactly what I did. I created a new Android project, spent next 30-40 mins and Voila! I could see it on my device and it looked beautiful. But then instantly I had a realization that not everyone can do what I did because it requires certain skills and knowledge whether for Web or Mobile. The content you'll see on Internet will mostly be in Naskh font because it's easier but suited for Arabic. Unless you know the exact websites or apps, you won't see Nastaliq script in action. The goal of any typography is to reduce irritation as much as possible because otherwise reader will more likely abandon it and Nastaliq makes reading Urdu content a more natural experience. Furthermore, it'll be your personal struggle to find all download links, license details, file size information and couple of more metrics.

This gave me enough motivation to build an application which will help anyone to visually see how different fonts
look like on a mobile device, why Nastaleeq should be our natural preference over Naskh script, and eventually helping decision makers in choosing the best one. This app will basically make this exercise a lot more hassle-free for you.

<img src="http://wahibhaq.github.io/img/projects/Urdu_Banner_Cover.png" width="600" height="300" align="middle">

Later, when I actually started my research I found out that it's so freaking difficult to even gather latest 
information on the related topics because either not many people have written or this information is all scattered. 
So I decided to put an additional effort to somehow compile it together in one place and it's now publicly available
on [Github](https://github.com/wahibhaq/urdu-font-comparator-app). I have tried to cover topics like what are the problems
and proposed solutions of adoption of Urdu on digital devices, Why Nastaleeq is a natural choice over Naskh and current 
status on different operations systems. In all honesty, my plan from day 1 was to make the project open-source and
available to use by everyone. It will help my portfolio but more importantly it was done to be a source of help for other 
Android devs from Pakistan and maybe it also inspire others to make their work available as open-source. There's no much 
point in keeping it private and then letting the project die or become obsolete. So, feel free to fork repo or use any part of the project code. 

This app and the research could be useful for following people:

* Urdu enthusiast who is just curious to know more about Nastaliq vs Naskh and understand the challenges faced.
* Project Owner who is responsible to manage publishing an Urdu version of new or existing app.
* Developer who wants to offer a section or complete app natively in Urdu content.
* Students who will like to research on related topic and somehow want to reuse any part of the app.
* If you are an Android developer and just want to explore how things are done in the app. Maybe fork it and contribute with improvements :) 

I have been working on this research and the Android app since Feb 2017 and got the first version launched on July 24th, 2017. So, overall, many people helped me in some way or another during this 6 month journey and I'm thankful to all of them. I have tried to mention all of them in [Contributors list](https://github.com/wahibhaq/urdu-font-comparator-app/blob/master/CONTRIBUTORS.md).

I would really appreciate if you could:

1. Share this post on Facebook, Twitter, LinkedIn and specially with those who care about writing and publishing Urdu content. 
2. Install the app from [Google Play](https://play.google.com/store/apps/details?id=com.androidistan.urdufontcomparator), 
rate different fonts (this data will be helpful) and leave a review on Google Play (check 'Rate this app' in top right menu)
3. If you want to read or share the details of the study done, checkout 
[README page](https://github.com/wahibhaq/urdu-font-comparator-app/blob/master/README.md)


P.S: I know it's kind of ironic that I wrote this post in English while talking about Urdu but I hope you understand that I also want it to be read by my International friends and followers. 
