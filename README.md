# DOMX

<link rel="icon" type="image/svg+xml" href="images/domx-logo.svg" />

`DOMX` is an approach to building modern web applications using the DOM, browser,
and patterns morso than relying on frameworks.

## Platform Evolution

Historically the web has seen a common pattern. 

We start with proprietary home grown solutions. Some of those solutions
may end up in a library that is shared by the community.
And finally, the browser platform provides its own solution. 

<div style="text-align:center;">
    <img src="images/platform-evolution.svg" style="width:100%">
</div>

### Stage Characteristics

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

There are significant long term benefits to sticking with the platform.



### Examples
This is not an exhaustive list by any means and there are many libraries you could add.

- DOM querying 
  - **Libraries** - JQuery, Prototype (add more and years)
  - **Browser** - querySelector, querySelectorAll (2010) 
- HTTP Requests
  - **Libraries** - [JQuery](https://api.jquery.com/category/ajax/) - 2006, [prototype](http://api.prototypejs.org/ajax/Ajax/index.html) - 2005
  - **Browser** - ajax, fetch (2015) 
- String interpolation
  - **Proprietary** - Array.join, [Crockfords .supplant](https://gist.github.com/pbroschwitz/3891293)
  - **Libraries** - [prototype](http://api.prototypejs.org/language/String/prototype/interpolate/index.html)
  - **Browser** - Template literals - `` when? 
- Promises 
  - **Libraries** - JQuery Deferred, year?, Prototype?
  - **Browser** - Promise (2011-2015), Async await – could not be done by libraries 
- Collection Utilities
  - **Libraries** - Underscore, Lowdash, Scoreunder  
  - **Browser** - Array.map, reduce, filter, find (2010-2015)
- Modules - code packaging and delivery and script loaders 
  - **Libraries** - CommonJs Modules 2009, AMD modules (2010) - similar to CommonJs but adds asynchronous support. Require (2010)
  - **Browser** - ES Modules:  2017 
- Date Manipulation 
  - **Libraries** - Datejs, Moment, Luxon, Dayjs, Date-fns, Spacetime 
  - **Browser**: [Temporal](https://2ality.com/2021/06/temporal-api.html ); New platform specific date object at Stage 3.
- Animation
  - **Libraries** - JQuery, prototype, Anime.js, Velocity. Js, Popmotion, Three. Js, GreenSock JS, AniJS, Mo. Js, Vivus. js. 
  - **Browser** - Web Animation API – Spec 2012, Chrome/Firefox 2014 - Experimental 
- UI Components
  - **Libraries** - JQueryUI, Backbone, Angular, Ember, React, Vue
  - **Browser** - Platform - 2017 
- State Management 
  - **Libraries** - Redux, Mobx, Recoil, NgXS, NgX 
  - **Browser** - Only development patterns
- URL Routing 
  - **Libraries** - Ember router, Angular router,
  - **Browser** - History API 


### Resistance to change 
Each step going from Proprietary -> Library -> Platform runs up against resistance before adoption. 

The larger companies backing the Library the higher the resistance due to investment. 

But would you still be on prototype.js today? 
 
#### Reasons to not change
What are reasons to stick with the old ($, _, vue, require?) 

Familiar, was successful, dont know another way, learning something new will take time, code already uses the old thing, dont want to train a bunch of devs 

Still the web moves forward - where will you be in 5-10 years? 


### Conclusion
- New language possibilities without transpiling (async/await example) 
- Standards 
- 1 standard 

 Why do we need jQuery when we have querySelectorAll, fetch, and Promise. Why do we need underscore when we have Array.map, .reduce, .find, etc. Why do we need require when we have import. Why do we need any number of UI component builders when we have custom elements? 

Two things that stand out on the list is a router and state management since the platform provides us with the tools to do these things but the patterns may not be as well known.

How to use the DOM for SDDF 



# State Management

The DOMX approach to state management embraces the unidirectional data flow pattern popularized by `FLUX` and `Redux` but relies on API's that already exist in the DOM.



## Use Cases
Why would you consider using a state management solution?
In many cases you do not need one.
For simple CRUD applications with little business logic and clear data boundaries
can manage without any added complexities.

There are a few conditions
- Want a slide to consider the use case and benefits 
- Rationalizing complex data structures and flow 
- Centralizing and decoupling data 
- What does that give us 
- Predictable state from many moving parts 

## How to Implement

## Comparisons 

### Flux
What problems does flux solve? 


<div style="text-align:center;max-width:400px;margin:0 auto;">
<img src="images/uddf-patterns-flux.svg" style="width:360px">
</div>




### React / Redux

<div style="text-align:center;max-width:400px;margin:0 auto;">
    <img src="images/uddf-patterns-react-redux.svg" style="width:360px">
</div>

### DOM Flux

<div style="text-align:center;max-width:400px;margin:0 auto;">
<img src="images/uddf-patterns-dom-flux.svg" style="width:360px">
</div>


---
<div style="text-align:center;">
    <img src="images/domx-logo.svg" style="max-width:150px;margin:2rem;">
</div>