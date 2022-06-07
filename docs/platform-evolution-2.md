---
layout: page
title: Platform Evolution (2 of 2)
permalink: /platform-evolution-2
---

# When the Platform is not Enough
Of course, there will always be a need for libraries. No one wants to build the 483rd date
component by hand and if there is need for complicated animations the Web Animation API or
Canvas may not cut it.

At the same time there may be ways to stay close to the platform without investing heavily
in proprietary solutions.

### Examples
#### State Management
One example is State Management. The unidirectional data flow pattern popularized
by Flux, then Redux (and others) can be achieved using window.dispatchEvent as a dispatcher
and DOM events as actions. The store can simple be an HTML component that contains state and 
listens to the DOM events.

See
- [State Management](/state-management)
- [Data Elements](/data-elements)


#### Client Side Routing
Routing can be more difficult since the History API only provides us with very basic
methods for updating or replacing the current URL.

Any solution that is used should therefore be built in a way that is easy to 
manage, monitor, and upgrade.

There are simple libraries that provide enough of what is needed such as
[Navigo](https://github.com/krasimir/navigo) or you can draw inspiration from
examples such as [A modern JavaScript router in 100 lines](https://krasimirtsonev.com/blog/article/A-modern-JavaScript-router-in-100-lines-history-api-pushState-hash-url)

The 100 lines example would be smaller if not supporting hash links and using a global
DOM click handler to test link clicks against routes and using .preventDefault() over
a setInterval timer.

See
- [Client Side Routing](/client-side-routing)
- [@domx/router](https://github.com/domxjs/domx/tree/master/packages/Router)


#### UI Component Libraries
Most teams will not want to build buttons, date pickers, sliders, inputs, etc. by hand.

However, when considering what to use for a UI component library it is important to know
what the UI will require. Some considerations to keep in mind are:
- Can you get away with light CSS or a lightweight skinning library with minimal JavaScript.
- Look for libraries that have few or no dependencies. There are a handful
that use Web Components that leverage the platform over something like VDOM or
other proprietary solutions.
- Invest in skinning your library to match your applications style so switching out or combining
libraries is not impossible.
- Create your own component library that combines all of the above using something like [Storybook](https://storybook.js.org/). This is especially useful if you are building multiple applciations
that need to share the same style.


#### HTTP Calls
For some, using the `XMLHttpRequest` object directly is taboo; but why?
It's easy enough to wrap a simple ajax call in a promise.

```js
const request = (url, {method, body, headers}) => new Promise((resolve, reject) => {
    const xhr = new XMLHttpRequest();
    xhr.open(method || "GET", url);
    if (headers) {
        Object.keys(headers).forEach(key => {
            xhr.setRequestHeader(key, headers[key]);
        });
    }
    xhr.onload = () => {
        if (xhr.status >= 200 && xhr.status < 300) {
            resolve(xhr.response);
        } else {
            reject(xhr.statusText);
        }
    };
    xhr.onerror = () => reject(xhr.statusText);
    xhr.send(body);
});
```

Using `fetch` is also fairly straight forward. 

A potential complication arrises when attempting to standardize on things such as errors
and timeouts.

These types of things tend to be specific to the application and each HTTP call should
handle the potential side effects of a non successful response.

Even so, standardized global errors can be handled by triggering a DOM event and listening
for it at the window to provide 404 pages or toast messages. 


---
The future is the past - we created frameworks that solve problems of yesterday,
now they get in the way of solutions for today. 
