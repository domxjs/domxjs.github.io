# DOMX

<link rel="icon" type="image/svg+xml" href="images/domx-logo.svg" />

`DOMX` is an approach to building modern web applications using the DOM, browser,
and patterns morso than relying on frameworks or libraries.

## Platform Evolution

Historically the web has seen a common pattern. 

We start with proprietary home grown solutions. Some of those solutions
may end up in a library that is shared by the community.
And finally, the browser platform provides its own solution. 

<div style="text-align:center;">
    <img src="images/platform-evolution.svg" style="width:100%">
</div>

## Stage Characteristics

<table>
    <tr>
        <th style="text-align:left">Proprietary</th>
        <th style="text-align:left">Library</th>
        <th style="text-align:left">Browser Platform</th>
    </tr>
    <tr>
        <td>Home grown</td>
        <td>More common</td>
        <td>Standard</td>
    </tr>
    <tr>
        <td>Slower</td>
        <td>Faster</td>
        <td>Fastest</td>
    </tr>
    <tr>
        <td>Least secure</td>
        <td>More secure</td>
        <td>Most secure</td>
    </tr>
    <tr>
        <td>More code to deliver</td>
        <td>Less code to deliver</td>
        <td>No code to deliver</td>
    </tr>
    <tr>
        <td>Write/manage/support</td>
        <td>Version upgrades</td>
        <td>Backwards compatible</td>
    </tr>
</table>

## Examples
This is not an exhaustive list, and there are many libraries and features that could be added.

- DOM querying 
  - **Libraries** - Prototype (2005), JQuery (2006)
  - **Browser** - querySelector, querySelectorAll (2010) 
- HTTP Requests
  - **Libraries** - [prototype](http://api.prototypejs.org/ajax/Ajax/index.html) (2005), [JQuery](https://api.jquery.com/category/ajax/) (2006)
  - **Browser** - Ajax (2001), fetch (2015) 
- String interpolation
  - **Proprietary** - Array.join, [Crockfords .supplant](https://gist.github.com/pbroschwitz/3891293)
  - **Libraries** - [prototype](http://api.prototypejs.org/language/String/prototype/interpolate/index.html)
  - **Browser** - Template literals (2015)
- Promises 
  - **Libraries** - Mochikit (2005), Dojo (2006), CommonJs (2009), JQuery Deferred (2010)
  - **Browser** - Promise (2011-2015), Async/await - language feature (2016) 
- Collection Utilities
  - **Libraries** - Underscore (2019), loadash (2012), Ramda (2013)  
  - **Browser** - Array.map, reduce, filter, find, etc. (2010-2015+)
- Modules - code packaging and delivery and script loaders 
  - **Libraries** - CommonJs Modules (2009), AMD modules (2010), Require.js (2010)
  - **Browser** - ES Modules (2017) 
- Date Manipulation 
  - **Libraries** - Datejs (2007), Moment (2011), Luxon (2017), Dayjs (2018), Date-fns (2016), Spacetime (2017)
  - **Browser**: [Temporal](https://2ality.com/2021/06/temporal-api.html); new platform specific date object at Stage 3.
- Animation / Canvas
  - **Libraries** -  prototype (2005), JQuery (2006-2014), Three.Js (2012), Velocity.Js (2014), Popmotion (2015), Mo-Js (2015), Vivus (2015), Anime.js (2016),  GreenSock (2017) 
  - **Browser** - Canvas (2010), Web Animation API – Spec 2012, Chrome/Firefox 2014 - Experimental 
- UI Components
  - **Libraries** - JQueryUI (2007), ExtJs (2007), Backbone (2010), Angular (2010), Ember (2011), React (2013), Webix (2013), Vue (2014), Svelte (2016), SolidJS (2018)
  - **Browser** - Custom Elements with templates and Shadow DOM (2017) 
- State Management
  - **Proprietary** Patterns: Observerables, Repositories, Pub/Sub, Flux, UDDF, DDD, etc.
  - **Libraries** - Redux (2015), RxJs (2015), Vuex (2015), Mobx (2016), Akita (2018), Recoil (2020), NgXS (2018), Hookstate (2019) 
  - **Browser** - Only patterns and API's such as localStorage, sessionStorage, IndexDB
- URL Routing 
  - **Libraries** - Ember router (2011), React router (2014), Angular router (2015), navigo (2015), tildeio router (2016)
  - **Browser** - History API - push/replace state (2010)


Why do you need a framework when all of this is built into the browser? There are
significant long term benefits to sticking with the platform as the
first choice when possible. Standards, backwards compatibility, security, speed.

It does not take any longer to learn how to develop on the browser platform than to learn
any other library or framework. And those skills are transferrable.

In many cases there is a strong argument to be made that when using libraries and frameworks, the additional proprietary complexity can add a significant amount of more code and immediate technical debt.


## Resistance to change 
Each step going from proprietary to library to platform runs up against resistance before adoption. The larger the company backing the library, the higher the resistance due to investment. 

But would you still choose to use prototype.js today? Or choose to use require over import on
any new project?

In some cases we hold onto the past because it is familiar, or we had prior success doing it that way. Learning something new takes time and our current code base already uses the old
thing and we do not want to train devs on the new thing.

And that is part of the beauty of learning and using the platform to its fullest.
It integrates with any technology because it is already there. Anyone can
start today without downloading anything from NPM.


## Summary
Why do we need jQuery when we have querySelectorAll, fetch, and Promise. Why do we need Underscore when we have Array.map, .reduce, .find, etc. Why do we need require when we have import. Why do we need any number of UI component builders when we have Custom Elements? 

Keep it simple. Prefer standards and patterns to proprietary libraries and frameworks.

Invest knowledge in the platform, it is here for the long haul.

And still the web moves forward; what will you be using in 5-10 years? 


## When the Platform is not Enough
Of course, there will always be a need for libraries. No one wants to build the 483rd date
component by hand and if there is need for complicated animations the Web Animation API or
Canvas may not cut it.

At the same time there may be ways to stay close to the platform without investing heavily
in prorprietary solutions.

### Examples
#### State Management
One example is State Management. The unidirectional data flow pattern popularized
by Flux, then Redux (and others) can be achieved using window.dispatchEvent as a dispatcher
and DOM events as actions. The store can simple be an HTML component that contains state and 
listens to the DOM events.

**[State Management Using the DOM](./state-management.md)**

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

---
The future is the past - we created frameworks that solve problems of yesterday,
now they get in the way of solutions for today. 
<div style="text-align:center;">
    <img src="images/domx-logo.svg" style="max-width:150px;margin:2rem;">
</div>

