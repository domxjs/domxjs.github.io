---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<link rel="icon" type="image/svg+xml" href="assets/domx-logo.svg" />

`DOMX` is an approach to building modern web applications using the DOM, browser,
and patterns morso than relying on frameworks or libraries.

Building a web application today is like building a [Rube Goldberg machine](https://en.wikipedia.org/wiki/Rube_Goldberg_machine). If [this](https://www.youtube.com/watch?v=qybUFnY7Y8w) feels like
your development experience then perhaps it is time to re-think and simplify.


## DOCS
- [Platform Evolution](/platform-evolution)
- [When the Platform is not Enough](/platform-evolution-2)
- [State Management](/state-management)
- **[Data Elements](/data-elements)** (on GitHub)


<div class="blurbc">
<div class="blurb">
    <h3>Platform Evolution</h3>
    <p>
    Historically the web has seen a common pattern. 
    </p>
    <p>
    We start with proprietary home grown solutions. Some of those solutions
    may end up in a library that is shared by the community.
    And finally, the browser platform provides its own solution. 
    </p>
    <a href="/platform-evolution">Read more</a>
</div>

<div class="blurb">
    <h3>When the Platform is not Enough</h3>
    <p>
    Of course, there will always be a need for libraries. No one wants to build the 483rd date
    component by hand and if there is need for complicated animations the Web Animation API or
    Canvas may not cut it.
    </p>
    <p>
    At the same time there may be ways to stay close to the platform without investing heavily
    in prorprietary solutions.
    </p>
    <a href="/platform-evolution-2">Read more</a>
</div>

<div class="blurb">
    <h3>State Management</h3>
    <p>
    The DOMX approach to state management embraces the unidirectional data flow pattern popularized by `FLUX` and `Redux` but relies on API's that already exist in the DOM.
    </p>
    <a href="/state-management">Read more</a>
</div>

<div class="blurb">
    <h3>Data Elements</h3>
    <p>
    The <code>DataElement</code> base class provides for a Flux/Redux style unidirectional data flow state management pattern using DOM events and custom elements.
    </p>
    <p>
    By utilizing the DOM and custom elements the footprint is small and 
    performance is fast since communication happens through
    DOM events and not a JavaScript library.
    </p>
    <a href="/data-elements">Read more</a>
</div>
</div>
