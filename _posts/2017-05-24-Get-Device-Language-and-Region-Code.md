---
layout:     post
title:      "Get Device Language and Region Code"
date:       2017-05-24 10:00:00
author:     "Sasha Prokhorenko"
tags: [ios, swift]
---
From time to time I need to send Language ISO (or something like this) to a server as a parameter.
Here is a little function which can handle this:

{% highlight swift %}

  func getLanguageISO() -> String {
    let locale = Locale.current
    guard let languageCode = locale.languageCode,
      let regionCode = locale.regionCode else {
        return "de_DE"
    }
    return languageCode + "_" + regionCode
  }

{% endhighlight swift %}