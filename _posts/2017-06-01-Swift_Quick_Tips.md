---
layout:     post
title:      "Swift Quick Tips"
subtitle:   "Multi-Line String Literals "
date:       2017-06-02 10:00:00
author:     "Sasha Prokhorenko"
header-img: "img/swift_quick _tips_2.png"
excerpt_separator:  <!--more-->
---
Only a few days left before WWDC 2017. I hope that we’ll see a lot of great and useful stuff, besides Swift 4, from Apple which can help us to make the world a better place.

One of the exciting features of upcoming Swift 4 is Multi-Line String Literals. I often need a quick way to create a prototype app with JSON data. Usually, I need to save data to local JSON file and then read from file or use network layer. That takes time. In Swift 4 we can use [Multi-Line String Literals](https://unsplash.com). 

<b>Example: </b>
I used [http://beta.json-generator.com](http://beta.json-generator.com) to generate fake JSON data for this example. The result JSON looks like:
![JSON]({{ site.url }}/img/swift_quick _tips_2_1.png)
[sample.json](https://gist.github.com/minikin/2ab9c40a78fdab4f78dcc17776bcf8e3)

Previously it wasn’t possible to use such strings like string literals.
In Swift 4 you can just copy/past it like this:

`"""  JSON/XML/OTHERS COMPLEX STRINGS """`
![Multi-Line String Literals.playground]({{ site.url }}/img/swift_quick _tips_2_2.png)
[Multi-Line String Literals.playground](https://www.dropbox.com/sh/m1idofs0jl28go0/AAAeh8tXaLiiBNw1u5ZSsyPAa?dl=1)
