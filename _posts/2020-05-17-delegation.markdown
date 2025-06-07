---
layout: post
title:  "Delegation"
date:   2020-05-17 09:01:36 -0700
categories: jekyll update
mathjax: true
---
The definition that made most sense was from <a href="https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CocoaFundamentals/CocoaDesignPatterns/CocoaDesignPatterns.html">developer.apple.com</a>. "Delegation is a mechanism by which a host object embeds a weak reference to another object (its delegate) and periodically sends messages to the delegate when it requires its input for a task." 
<br>
<br>
For example, <i>NSWindow</i> has a weak reference to its delegate object, <i>delegate</i>, which conforms to the protocol <i>NSWindowDelegate</i>. <i>NSWindowDelegate</i> defines a set of optional methods that the delegate can implement to respond to various messages sent by the window object. Since the methods are optional, <i>NSWindow</i> will check if its delegate implemented them by calling respondToSelector. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Motivation</h3>
Why delegation? why can't we use inheritance instead? Delegation reduces coupling between classes. There is no need for our object to subclass <i>NSWindow</i> in order to define additional behavior. We just become a delegate of <i>NSWindow</i> to receive all the critical messages we're interested in and then define our own custom behaviors on top of it.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
This is an extremely simple example to see how delegation might work. Suppose we have a view with a simple button. When the button is pressed, we move to another view. In the first view controller we have the following:
{% highlight c++ %}
class ViewController: UIViewController, SubViewControllerDelegate {
    override func viewDidLoad() {
        super.viewDidLoad()
        let button = UIButton(frame: CGRect(x: 100, y: 100, width: 100, height: 50))
        button.backgroundColor = .green
        button.setTitle("Press", for: .normal)
        button.addTarget(self, action: #selector(pressed), for: .touchUpInside)
        self.view.addSubview(button)
    }
	@objc func pressed() { // when the button is pressed, move to AnotherViewController
        let host = HostViewController()
        host.delegate = self // we are the delegate of host
        self.present(sub, animated: true, completion: nil)
    }
}
{% endhighlight %}

In the second view controller (host), we have a button. When we press the button, we want to let the first view controller know that it's been pressed. To do so, we create a weak delegate reference that lives with us, the host controller. This delegate must conform to a protocol that we design. <i>someMessage</i> is the way we want to communicate with the delegate. 

{% highlight c++ %}
public protocol HostViewControllerDelegate: class {
    func someMessage(_ message: String)
}
{% endhighlight %}

The delegate will implement <i>someMessage</i>. The host will then call <i>someMessage</i> on the delegate to pass it a message that says "hey, the button has been pressed!!".

{% highlight c++ %}
class HostViewController: UIViewController {
    public weak var delegate: HostViewControllerDelegate? // our delegate

    override func viewDidLoad() {
        let button = UIButton(frame: CGRect(x: 100, y: 100, width: 100, height: 50))
        button.backgroundColor = .red
        button.setTitle("World", for: .normal)
        button.addTarget(self, action: #selector(pressed), for: .touchUpInside)
        self.view.addSubview(button)
    }

    @objc func pressed() {
        delegate?.someMessage("hey, the button has been pressed!!")
    }
}
{% endhighlight %}

<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
- <a href="https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612">Design Patterns</a>
- <a href="https://www.amazon.com/Cocoa-Design-Patterns-Erik-Buck/dp/0321535022">Cocoa Design Patterns (Book)</a>
- <a href="https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CocoaFundamentals/CocoaDesignPatterns/CocoaDesignPatterns.html">Cocoa Design Patterns (Apple Docs)</a>
<br>
<br>















