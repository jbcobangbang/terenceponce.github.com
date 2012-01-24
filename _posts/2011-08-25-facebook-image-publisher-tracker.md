---
layout: post
title: "Facebook Image Publisher Tracker"
date: 2011-08-25 12:00:00
category: programming
tags:
 - Java
 - Spring
 - Google App Engine
 - Maven
---

Hi there! It’s been a while since I made an article. I got pretty busy and kinda lazy over the past few months so I completely forgot that I have a blog going on.

So the last article that I made was about [using Google App Engine](http://terenceponce.github.com/2011/03/26/a-noobs-attempt-on-google-app-engine-using-java-and-maven-part-2/). I stopped that project because it got pretty complicated the moment I tried using the Datastore. So now, I decided to build something simple, something that doesn’t require a database to run.

Recently, I found out that you can trace a Facebook image back to its publisher based on the image’s URL. Obviously, the image should come from Facebook’s content deliver network or CDN as people usually describe it. It’s no secret, really. I found out how immediately after my first Google search. I’m pretty sure revealing how is kind of unethical and on a moral gray area, but hey, the information is already out there. It’s not like I can make it any worse by posting it here. Besides, I trust that any reader of this blog (if there’s really anyone reading this) would be responsible enough not to use it for evil.

Let’s say, for example, I posted this [Facebook picture of me](https://fbcdn-sphotos-a.akamaihd.net/hphotos-ak-snc6/63442_472293192932_636557932_5746749_150701_n.jpg) somewhere on the Internet. At the 3rd level of the image link, there’s a set of numbers separated by an underscore (63442_472293192932_636557932_5746749_150701_n.jpg). These numbers are actually time stamps, but among those time stamps is the profile ID of the publisher of the image. What you want to do is to get the 3rd one (636557932), which is the profile ID, and type the link in your browser:

{% highlight html %}
http://facebook.com/profile.php?id=<insert profile ID here>/
{% endhighlight %}

That wasn’t so hard right? I’m pretty sure anyone persistent enough would be able to figure it out on their own.

After I learned how to do that, I thought it would be fun to make a simple tool to automate the process since I’m too lazy to type it in the address bar every time. Then I realized that it’s pretty easy to make it into a Google App Engine app, so I did.

Since I didn’t really want this article to be lengthy and cause people to get bored, I decided to skip with the code discussion and just get on with showing you the actual software itself. The tool can be found [here](http://aquamodena.appspot.com/) and the source code for the whole project can be found [here](https://bitbucket.org/terenceponce/facebook-image-publisher-tracker/src).

