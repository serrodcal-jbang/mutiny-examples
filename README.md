## jbang project for Mutiny by examples

This is a "virtual" project directory for the jbang script Mutiny.

This lets you get content assist, debugging, etc. for Java in most modern editors and IDE's.

JBang tested this to work in the following IDE's:

* Eclipse
* IntelliJ
* Visual Studio Code
* Netbeans
* vi
* emacs

## Enjoy

Have fun and if you like this consider following [@jbangdev](http://twitter.com/jbangdev) and give a
star to [jbangdev/jbang](https://github.com/jbangdev/jbang).

If you have issues or suggestions please [open an issue](https://github.com/jbangdev/jbang/issues/new).

With love, <br/>
[jbang.dev](https://jbang.dev)

## Steps followed to generated and to use this scripting project

Project created with:

> jbang init Mutiny.java

Project edited with:

> jbang edit --open=code --live Mutiny.java

Execute this project with:

> jbang Mutiny.java

## About Mutiny

Mutiny is an Intuitive Event-Driven Reactive Programming Library for Java. It provides a simple but powerful asynchronous development model that lets you build reactive applications.

Mutiny is:

* Event-Driven: Mutiny places events at the core of its design. With Mutiny, you observe events, react to them, and create elegant and readable processing pipelines. A PhD in functional programming is not required.
* Navigable: Even with smart code completion, classes with hundred of methods are confusing. Mutiny provides a navigable and explicit API driving you towards the operator you need.
* Non-Blocking I/O: Mutiny is the perfect companion to tame the asynchronous nature of applications with non-blocking I/O. Declaratively compose operations, transform data, enforce progress, recover from failures and more.

Because of Mutiny is a reactive programming library, we have to provide a definition about what's mean reactive programming:

> Reactive programming is about programming with data streams.

That’s it. Reactive programming is about streams and especially, observing them. It pushes that idea to its limit: with reactive programming, everything is a data stream.

With reactive programming, you observe streams and implement side-effects when something flows in the stream.

It’s asynchronous by nature as you don’t know when the data is going to be seen. Yet, reactive programming goes beyond this. It provides a toolbox to compose streams and process events.

But, What's Reactive Stream?

Well, it's a standard for asynchronous stream processing with a non-blocking back pressure.

This standard provides an API based on four concepts:

* Subscription: A simple interface acting as a kind of channel description and providing two methods:
    * `cancel()`: Used by a subscriber to cancel its subscription
    * `request(long)`: Used by a subscriber to request n messages to a Publisher
* Publisher: A generic interface providing a single `subscribe(Subscriber)` method. At first glance considering the original publish/subscribe pattern, it might be strange for a publisher to subscribe to a subscriber. But this is actually the strength of Reactive Streams, the capability for a publisher to adapt its flow of data according to a subscriber.
* Subscriber: A generic interface providing 4 methods:
    * `onComplete()`: Notify the subscriber when a publisher is closed
    * `onError(Throwable)`: Notify the subscriber when a publisher is closed with an error state
    * `onNext(T)`: Notify the subscriber a message was sent. If everything goes right, after having processed a message, the subscriber will usually invoke then `Subscription.request(long)`.
    * `onSubscribe(Subscription)`: Notify the subscriber that a publisher just started a subscription (through the Publisher.subscribe(Subscriber) method). This is also a way for the subscriber to keep a reference on the Subscription object provided.
* Processor: A simple interface extending Publisher and Subscriber interfaces. In other words a Processor can acts as both a Publisher and a Subscriber.

## References

* [Smallrye Mutiny](https://smallrye.io/)
* [Reactive Streams](https://www.reactive-streams.org/)
* [An Introduction to Reactive Streams](https://teivah.medium.com/an-introduction-to-reactive-streams-fad58e21c795)
