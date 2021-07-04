---
layout: post
title: Live reload with Compose Web - see your progress instantly
date: 2021-06-16 00:46:37
description: Compose Web can already make your progress visible at the moment of writing
img: 2021-06-16-live-reload-with-compose-web/jetpack-compose.png
tags: [compose, compose-web]
---

### Live reload is available for KotlinJS projects for quite a while - I got to use it a while ago while making a web app with react-kotlin.

After trying it in Compose Web, it worked seemlessly out of the box.

The trick is to add `--continuous` argument to the gradle task which runs the app in the browser.

### In terminal:

If your project is a single module:
{% highlight shell %}
./gradlew jsBrowserDevelopmentRun --continuous
{% endhighlight %} 

For multi-module projects:
{% highlight shell %}
./gradlew :modulename:jsBrowserDevelopmentRun --continuous
{% endhighlight %}

### In IntelliJ:

You need to edit task configuration in Gradle panel.

![Gradle panel screenshot](/assets/img/2021-06-16-live-reload-with-compose-web/gradle-panel.png)

![Edit configuration screenshot](/assets/img/2021-06-16-live-reload-with-compose-web/edit-configuration.png)

Alternatively, on older IntelliJ versions it may look like this:

![Old intellij screenshot](/assets/img/2021-06-16-live-reload-with-compose-web/old-intellij.png)

When a change is detected, Gradle will deploy the updated site. To force a reload, press `Ctrl/Cmd+S` to save the file.

[For more information on the continuous compilation visit JetBrains site.](https://kotlinlang.org/docs/dev-server-continuous-compilation.html)

---