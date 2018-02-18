---
layout:     post
title:      "Host in-house private frameworks with CocoaPods"
description:  ""
date:       2018-02-17 10:00:00
author:     "Sasha Prokhorenko"
tags: [ios, swift, macos, cocoaPods, Xcode]
---

When you have frameworks which you need to share between iOS developers inside
a company without going public you can do it with a private [CocoaPods](https://cocoapods.org){:target="_blank"} repository.
In this blog post, I’m going to show you how to do so step by step.

- Create private repository on your company's Github, Bitbucket or Gitlab:
    ![Bitbucket]({{ site.url }}/img/blog/cocoapods/cp_1.png)
- Provide access for all your iOS team members.

- Add your private specs:

{% highlight bash %}

pod repo add specsName https://code.company.com/podspecs.git

{% endhighlight bash %}

_Note_ : It will be add to the pass  ```~/.cocoapods/repos ```

- When you have your pod ready, push your CocoaPod specs to remote:

{% highlight bash %}

pod repo push specsName MyPod.podspec

{% endhighlight bash %}

OR

{% highlight bash %}

pod repo push --allow-warnings specsName MyPod.podspec

{% endhighlight bash %}

- When you need to use your in-house pod, just add your private podspecs source and desire pod to Podfile

{% highlight ruby %}

source 'https://code.company.com/podspecs.git'
source 'https://github.com/CocoaPods/Specs.git' 
platform :ios, '11.0'

target 'MayApp' do
  use_frameworks!
  pod 'MyPod'
end

{% endhighlight ruby %}