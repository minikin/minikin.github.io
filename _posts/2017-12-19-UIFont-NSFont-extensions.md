---
layout:     post
title:      "UIFont/NSFont extension to handle custom fonts in Swift (iOS/macOS)"
description:  ""
date:       2017-12-19 10:00:00
author:     "Sasha Prokhorenko"
tags: [ios, swift, macos]
---
I’ve just finished watching interesting presentation [“To be! Or not? Optionals in practice”](https://www.youtube.com/watch?v=Q1Tayh4unMw){:target="_blank"} 
by [Rob Napier](https://twitter.com/cocoaphony){:target="_blank"}
And I’d like to share one of Rob’s good ideas how to handle custom fonts with UIFont extension + NSFont extension for macOS

Here is a code snippet for UIFont:

{% highlight swift %}

import UIKit

extension UIFont {
	private static func customFont(name: String, size: CGFloat) -> UIFont {
		let font = UIFont(name: name, size: size)
		assert(font != nil, "Can't load font: \(name)")
		return font ?? UIFont.systemFont(ofSize: size)
	}
	
	static func mainFont(ofSize size: CGFloat) -> UIFont {
		return customFont(name: "MyLovely-CustomFont", size: size)
	}
}

{% endhighlight swift %}

<b>and NSFont version:</b>

{% highlight swift %}

import Cocoa

extension NSFont {
	private static func customFont(name: String, size: CGFloat) -> NSFont {
		let font = NSFont(name: name, size: size)
		assert(font != nil, "Can't load font: \(name)")
		return font ?? NSFont.systemFont(ofSize: size)
	}
	
	static func mainFont(ofSize size: CGFloat) -> NSFont {
		return customFont(name: "MyLovely-CustomFont", size: size)
	}

}

{% endhighlight swift %}