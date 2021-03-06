---
layout: post
title: How to Create a Spring Boot Application using Kotlin and Gradle
author: thiago
date: 2018-03-10 15:00:00 +0300
description: How to Create a Spring Boot Application using Kotlin and Gradle # Add post description (optional)
image: assets/images/spring/spring-boot-and-kotlin-20180310.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Kotlin,Java,Spring,Spring Boot,blog]
categories: [ tutorial ]
featured: true
---

A few months ago I wrote an article showing how to create a simple Spring Boot application using Java, you can see it by [clicking here](https://thiagoteixeira.github.io/how-to-create-spring-boot-application).

Now, I am going to show you, how to create the same application using [Kotlin](https://kotlinlang.org/) and [Gradle](https://gradle.org/).

The requirements are:
 - [Gradle](https://gradle.org/) installed;
 - Text Editor installed, I recommend [Visual Studio Code](https://code.visualstudio.com/)
 

Now, you must go to the following website:
 * [Spring Initializr](https://start.spring.io/)
 
Choose to generate a **Gradle Project** with **Kotlin** and fill in the **group** and the **artifact** fields. Example:
 - **Group**: com.mydomain
 - **Artifact**: demo
 
In the **Search for dependencies** field fill in: **Web**

The options chosen will be as the image below:

![Spring Initializr Kotlin option]({{site.baseurl}}/assets/images/kotlin/how-to-create-spring-boot-with-kotlin-and-gradle/spring-initializr-options-chosen.png)

Now, click on the **Generate Project** button

So, download the ZIP file and unzip it.

Using a text editor ( I recommend [Visual Studio Code](https://code.visualstudio.com/)), open the demo folder.

---

We are going to create the web controller file named HelloWorldController.kt at `demo\src\main\kotlin\com\example\demo\\` folder:

![Spring Boot Kotlin Controller Hello World]({{site.baseurl}}/assets/images/kotlin/how-to-create-spring-boot-with-kotlin-and-gradle/hello-world-controller-file.png)


Your respective code will be:

{% highlight java %}
package com.example.demo

import org.springframework.web.bind.annotation.GetMapping
import org.springframework.web.bind.annotation.RestController

@RestController
class HelloWorldController {

    @GetMapping("/")
    fun index() = "Hello, World!"

}
{% endhighlight %}

---

Now, using the command prompt you can initialize the application using the command: `gradle bootrun`. It is going to use [Gradle](https://gradle.org/).
After the execution, you will see the success message referring to the initialization from an embedded Apache Tomcat.

**
<==========---> 80% EXECUTING [1m 40s]
> :bootRun **
**

So, access http://localhost:8080 in the web browser.

![Spring Boot Kotlin Controller Hello World in Browser]({{site.baseurl}}/assets/images/kotlin/how-to-create-spring-boot-with-kotlin-and-gradle/hello-world-browser-access.png)


Finally, your first Spring Boot application with Kotlin and Gradle was created.

Thanks for reading.