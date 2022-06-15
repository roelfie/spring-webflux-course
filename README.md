# spring-webflux-course
My notes of the Udemy course 'Reactive Programming with Spring Framework 5'

[Udemy course](https://www.udemy.com/course/reactive-programming-with-spring-framework-5/)

## 2. Reactive Programming

### 2.1 Reactive systems
The [Reactive Manifesto](https://www.reactivemanifesto.org/) states that _Reactive Systems_ are
* Responsive: The system responds in a timely manner if at all possible.
* Resilient: The system stays responsive in the face of failure.
* Elastic: The system stays responsive under varying workload.
* Message Driven: Reactive Systems rely on asynchronous message-passing to establish a boundary between components
  that ensures loose coupling, isolation and location transparency. This boundary also provides the means to
  delegate failures as messages.

#### Message-driven vs. Event-driven

| Message Driven                                                          | Event Driven                                                                                                       |
|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| A _message_ is an item of data that is sent to a specific destination.  | An _event_ is a signal emitted by a component upon reaching a given state.                                         |
| A message-driven system concentrates on addressable recipients          | An event-driven system focuses on addressable event sources.                                                       |
| Addressable recipients await the arrival of messages and react to them. | Notification listeners are attached to the sources of events such that they are invoked when the event is emitted. |

#### Protocols
Protocols can be classified by the shape of the exchange. The most common classes are:
* request–reply
* repeated request–reply (as in HTTP)
* publish–subscribe (SQS / SNS)
* stream (both push and pull)

### 2.2 Reactive Streams
[Reactive Streams](https://www.reactive-streams.org/) is an initiative to provide a standard for asynchronous stream 
processing with non-blocking back pressure.
* [Specifications](https://github.com/reactive-streams/reactive-streams-jvm)
* [JavaDoc](https://www.reactive-streams.org/reactive-streams-1.0.4-javadoc/org/reactivestreams/package-summary.html)

#### Implementations of reactive streams

* [Project Reactor](https://projectreactor.io/)
* [RxJava](https://github.com/ReactiveX/RxJava)
* [Java 9 Flow API](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/Flow.html)

#### Back pressure

Non-blocking [back pressure](https://www.reactivemanifesto.org/glossary#Back-Pressure) is an integral part of the
reactive streams model. As stated in [this blog post](https://blog.frankel.ch/backpressure-reactive-systems/):
Considering a fast data producer and a slow data consumer, backpressure is the mechanism that "pushes back" on the
producer not to be overwhelmed by data.

### 2.3 Project Reactor
[Project Reactor](https://projectreactor.io/) is an implementation of the Reactive Streams specification, for 
building non-blocking applications on the JVM. It offers: 
* two APIs which implement Reactive Extensions
  * [Flux](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Flux.html)
  * [Mono](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Mono.html)
* backpressure-ready network engines for HTTP/Websockets, TCP & UDP

### 2.4 Reactive Extensions (ReactiveX)
[ReactiveX](https://reactivex.io/) or 'Reactive Extensions' is a set of tools allowing imperative programming 
languages to operate on sequences of data regardless of whether the data is synchronous or asynchronous. 

Available in Java, JavaScript, Python and many more languages.

Defines a [vocabulary of operators](https://reactivex.io/documentation/operators.html).

### 2.5 Spring WebFlux

[Spring WebFlux](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html#spring-webflux) 
is Spring's reactive stack web framework. 
* non-blocking
* supports Reactive Streams backpressure
* allows for concurrency with a small number of threads; scales with fewer hardware resources
* default reactive library is Project Reactor


