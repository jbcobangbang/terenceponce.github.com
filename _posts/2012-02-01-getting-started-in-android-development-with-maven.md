---
layout: post
title: "Getting started in Android development with Maven"
date: 2012-02-01 13:00:00
category: programming
tags:
 - android
 - java
 - maven
---

I recently acquired a Sony Ericsson Xperia Play as my new phone. As what any sensible person will do in my situation, I decided to try my hand in Android development.

The first thing I did was to go to the [Android Developer website](http://developer.android.com "Android Developers") and read the instructions on [how to install the SDK](http://developer.android.com/sdk/installing.html "Installing the SDK"). One of my biggest pet peeves in software development is the dependency to a specific IDE/editor. I like coding in really simple text editors and relying on command line tools when I'm developing, so I tried finding a way to not have to use Eclipse for Android development.

Since I'm using Java, the obvious action was to use Maven and find a plugin that does the job. A quick Google search directed me to the [Maven Android Plugin](http://code.google.com/p/maven-android-plugin/). I haven't used it extensively, but so far, it solves my problem.

The easiest way to get started is by using [android-archetypes](https://github.com/akquinet/android-archetypes "Android-Archetypes") created by [akquinet](http://www.akquinet.de/en). Their archetypes are based on the Maven Android Plugin, so it is already included out of the box.

After trying out, I couldn't get it to work as it is. For some reason, the plugin is looking at the wrong place for the Android SDK (/home/username/android-sdk-directory/platforms), so I had to include the path explicitly in the pom.xml file.

{% highlight xml tabsize=4 %}
<plugin>
  <!-- omitted other code for brevity -->
  <configuration>
    <sdk>
      <path>/root/path/of/android/sdk</path>
    </sdk>
  </configuration>
</plugin>
{% endhighlight %}

Afterwards, you can execute Maven and deploy the app to a device connected to your computer using the following command:

{% highlight applescript %}
$ mvn clean install android:deploy
{% endhighlight %}

