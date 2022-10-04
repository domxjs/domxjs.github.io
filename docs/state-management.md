---
layout: page
title: State Management
permalink: /state-management
---

# State Management
The DOMX approach to state management embraces the unidirectional data flow pattern popularized by `FLUX` and `Redux` but relies on API's that already exist in the DOM.

See: <a href="/data-elements">Data Elements</a>

## Use Cases
Why would you consider using a state management solution?
In many cases you do not need one.
Simple / CRUD applications with little business logic and clear data boundaries
can manage without any added complexities.

As an application grows in complexity, the need for a solution first appears
as pain points in the development experience.

Some benefits for a state management solution include:
- Decoupling business logic from UI components
- Rationalizing complex data structures and flow 
- Centralizing business logic
- Improving code maintainability
- Applying architectural patterns

## Unidirectional Data Flow
A popular state management pattern for Web Applications is UDDF (unidirectional data flow).

This pattern keeps state in a consolidated location usually called a store.
UI components receive their state from the store and can dispatch actions
when things occur. The store handles the action and updates the state which 
then updates the UI components.

This ensures that there is only one way in which data is transferred to
other parts of the application and so helps with conceptualizing how the
application is built.

## Implementations 
There are many UDDF libraries, but lets take a look at two of them to illustrate the pattern.

### Flux
Early on the scene was the [Flux project from Facebook](https://facebook.github.io/flux/).
It inspired other libraries such as Redux and MobX.

Flux is not a library, instead it just popularized the pattern. Facebook
released a few utilities and a dispatcher for those who did not want to build it
for themselves since that is a core piece of the pattern.

<div style="text-align:center;max-width:400px;margin:0 auto;">
    <img src="assets/uddf-patterns-flux.svg" style="width:360px">
</div>


### React / Redux
Redux, on the other hand, is a full solution to the pattern and is meant to be used
with React though it is possible to use without it.

A primary difference with Redux is that it uses a functional programing paradigm
to change the the state in a store using reducers.

<div style="text-align:center;max-width:400px;margin:0 auto;">
    <img src="assets/uddf-patterns-react-redux.svg" style="width:360px">
</div>

Redux is not without its drawbacks however, to list a few:
- Most beginners complain about excessive boilerplate.
- Asynchronous code with thunks and sagas feels clunky and non intuitive for
such a common and simple need.
- It does not reduce view data coupling; any component can access any part of the state.
- RTK toolkit reduces boilerplate but adds complexity and indirection
- Steep learning curve.



## UDDF Using the DOM 
Since Flux is just a pattern, how can we implement the pattern using the tools
the platform already provides for us?

The central part of the pattern is the dispatcher. Does the platform provide us
with anything that we can use as a dispatcher? It does, and a very good one in fact.

**`dispatchEvent`**

The `dispatchEvent` method that is found on any DOM element and the window object
is a very efficient, time tested, fast, dispatcher that also includes
patterns and features beyond what you will typically find in any hand written
Flux dispatcher.


### DOM Flux
Using the DOM to implement the Flux pattern we have these pieces:
- The store is an HTMLElement that has a state property (can be named anything you choose).
- The store sets up event listeners for "actions".
- Actions are simply DOM events. A `CustomEvent` can be used to provide a payload 
with its `detail` property. Or better yet, use a subclassed DOM `Event` for better
type safety.

<div style="text-align:center;max-width:400px;margin:0 auto;">
    <img src="assets/uddf-patterns-dom-flux.svg" style="width:360px">
</div>

Using the DOM provides freedom in how the pattern is implemented
- A more traditional object oriented or DDD approach with classes can be achieved.
- A more functional approach (i.e. reducers) can also be used.
- One store or multiple stores can be used.
- Creating multiple stores that share a global/root state is not hard to implement
(similar to reacts context API); see: [Data Elements](/data-elements)


Here is an [Example application](https://github.com/jhorback/wcn-todo-app) with
three "Data Elements" to show different implementations.

Here is a more in depth example: [Harbor](https://github.com/jhorback/harbor).

Utilizing the browser platform and DOM has benefits that become apparent
when developing. When questions arise while using other libraries we are
required to look up library specific proprietary solutions. However, using the
DOM provides for simplicity and familiarity out of the box.
Everyone should now how DOM events are dispatched and handled.
Answers usually come in the form of "oh wait, this is just an HTML Element... I
know how those work". Solutions are flexible and can adapt to many development styles
and application needs however complex or simple.

