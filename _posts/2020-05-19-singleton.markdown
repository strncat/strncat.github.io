---
layout: post
title:  "Singleton"
date:   2020-05-19 09:01:36 -0700
categories: jekyll update
mathjax: true
---
This one is pretty straightforward. The singleton design pattern is used whenever there is a class where only one object is allowed to exist at any time. <i>UIApplication</i> is one example that uses this pattern.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
It is pretty straightforward as well to make a class with only one instance of itself. One way to do it is to create a static variable to hold the object and declare init to be private.
{% highlight c++ %}
public class Singleton {
    public static let shared = Singleton()
    private init() { }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
- <a href="https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612">Design Patterns</a>
- <a href="https://www.amazon.com/Cocoa-Design-Patterns-Erik-Buck/dp/0321535022">Cocoa Design Patterns (Book)</a>
- <a href="https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CocoaFundamentals/CocoaDesignPatterns/CocoaDesignPatterns.html">Cocoa Design Patterns (Apple Docs)</a>
- <a href="https://www.raywenderlich.com/1941154-fundamental-ios-design-patterns/lessons/18">Fundamental iOS Design Patterns</a>
<br>
<br>














