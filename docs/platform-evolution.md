---
layout: page
title: Platform Evolution (1 of 2)
permalink: /platform-evolution
---
# Platform Evolution
Historically the web has seen a common pattern. 

We start with proprietary home grown solutions. Some of those solutions
may end up in a library that is shared by the community.
And finally, the browser platform provides its own solution. 

<div style="text-align:center;">
    <img src="assets/platform-evolution.svg" style="width:100%">
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

- **DOM querying** 
  - Libraries - Prototype (2005), JQuery (2006)
  - Browser - querySelector, querySelectorAll (2010) 
- **HTTP Requests**
  - Libraries - [prototype](http://api.prototypejs.org/ajax/Ajax/index.html) (2005), [JQuery](https://api.jquery.com/category/ajax/) (2006)
  - Browser - Ajax (2001), fetch (2015) 
- **String interpolation**
  - Proprietary - Array.join, [Crockfords .supplant](https://gist.github.com/pbroschwitz/3891293)
  - Libraries - [prototype](http://api.prototypejs.org/language/String/prototype/interpolate/index.html)
  - Browser - Template literals (2015)
- **Promises**
  - Libraries - Mochikit (2005), Dojo (2006), CommonJs (2009), JQuery Deferred (2010)
  - Browser - Promise (2011-2015), Async/await - language feature (2016) 
- **Collection Utilities**
  - Libraries - Underscore (2019), loadash (2012), Ramda (2013)  
  - Browser - Array.map, reduce, filter, find, etc. (2010-2015+)
- **Modules** - code packaging and delivery and script loaders 
  - Libraries - CommonJs Modules (2009), AMD modules (2010), Require.js (2010)
  - Browser - ES Modules (2017) 
- **Date Manipulation**
  - Libraries - Datejs (2007), Moment (2011), Luxon (2017), Dayjs (2018), Date-fns (2016), Spacetime (2017)
  - Browser: [Temporal](https://2ality.com/2021/06/temporal-api.html); new platform specific date object at Stage 3.
- **Animation / Canvas**
  - Libraries -  prototype (2005), JQuery (2006-2014), Three.Js (2012), Velocity.Js (2014), Popmotion (2015), Mo-Js (2015), Vivus (2015), Anime.js (2016),  GreenSock (2017) 
  - Browser - Canvas (2010), Web Animation API – Spec 2012, Chrome/Firefox 2014 - Experimental 
- **UI Components**
  - Libraries - JQueryUI (2007), ExtJs (2007), Backbone (2010), Angular (2010), Ember (2011), React (2013), Webix (2013), Vue (2014), Svelte (2016), SolidJS (2018)
  - Browser - Custom Elements with templates and Shadow DOM (2017) 
- **State Management**
  - **Proprietary** Patterns: Observables, Repositories, Pub/Sub, Flux, UDDF, DDD, etc.
  - Libraries - Redux (2015), RxJs (2015), Vuex (2015), Mobx (2016), Akita (2018), Recoil (2020), NgXS (2018), Hookstate (2019) 
  - Browser - Only patterns and API's such as localStorage, sessionStorage, IndexDB
- **URL Routing** 
  - Libraries - Ember router (2011), React router (2014), Angular router (2015), navigo (2015), tildeio router (2016)
  - Browser - History API - push/replace state (2010)


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

Continue: **[When the platform is not enough](/platform-evolution-2)**