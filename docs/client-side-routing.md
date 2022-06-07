---
layout: page
title: Client Side Routing
permalink: /client-side-routing
githuburl: https://github.com/domxjs/domx/tree/master/packages/Router
---


# Client Side Routing


## Description
Often times routing begins and ends with following the boilerplate examples used in your web framework of choice. Routing may even be a feature that is tacked on haphazardly at the end of a development cycle when you realize your application is behaving strangely and need to do some patch work to fix some primary use cases. Or sometimes, even more tragically, routing may not be implemented at all. 

Even though browsers gave us the ability to solve for these problems with additions to the history API back in 2011, today, routing remains one of the primary sources of usability issues in our web applications. 

## The Struggle
The reason why routing remains a struggle for many of us when building web applications starts with the feature requirements. Rarely do project managers or those writing the features add acceptance criteria to cover routing.

Many times, it is only after the fact that we discover issues when navigating because each feature, page, tab was implemented in isolation. They work fine when testing the individual feature, but in standard use cases, fall short when navigating between features.


<!--
## Examples of Good and Bad Routing
We will cover a myriad of good and bad examples of routing, and go over some simple rules to drastically improve your users experience with a few "easy" to implement tricks. 

## How a Router is Built
We will also take a look at the basics of how a router is built.

## What to Look for in a Router
so we can better understand what features to look for when choosing a router. And if you are already using a first class router, what features it may already have so that you can take full advantage of them.

## How to use the history API directly
And finally, for simple applications, how to use the history API directly to solve for the most common pitfalls. 
!-->

## The Challenge
The challenge was to build a router using native web technologies that could be declared in simple HTML markup.

Standard HTML links should work as expected without the need for a proprietary component wrapper.

The router should know the difference between a link that can be handled by the router simply by referencing the routes defined.

To see a full list of routing goals, take a look at the `DOMX` feature implementation on GitHub:
<a href="https://github.com/domxjs/domx/tree/master/packages/Router">DOMX Router</a>.


## DOMX Router Diagram
This diagram was created to work through the various use cases of a router.
<div style="text-align:center;max-width:400px;margin:0 auto;">
    <a href="assets/Router.drawio.svg" target="__blank">
        <img src="assets/Router.drawio.svg" style="width:460px">
    </a>
</div>