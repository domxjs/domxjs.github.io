# State Mangement
State Management using the DOM.

The DOMX approach to state management embraces the unidirectional data flow pattern popularized by `FLUX` and `Redux` but relies on API's that already exist in the DOM.

## Use Cases
Why would you consider using a state management solution?
In many cases you do not need one.
Simple / CRUD applications with little business logic and clear data boundaries
can manage without any added complexities.

As an application grows in complexity the need for a solution first appears
as pain points in the development experience.

There are a few benifits for considering some sort of state management practices.
- Rationalizing complex data structures and flow 
- Centralizing business logic
- Improving code maintainability
- Applying architectural patterns
- Decoupling buisiness logic from UI components

## Unidirectional Data Flow
A popular state management pattern for Web Applications is unidirectional Data Flow.

What problems does this solve?
- This helps with conceptualizing how the application is built.
- Fill this out...

Alternatives?


Flux was early on the scene with Facebook and inspired other libraries such as Redux and MobX.
Many applications have used this pattern with success.
But is there a way to use this pattern without a library, just equiped with the DOM?


## Comparisons 
There 

### Flux

<div style="text-align:center;max-width:400px;margin:0 auto;">
    <img src="images/uddf-patterns-flux.svg" style="width:360px">
</div>


### React / Redux
Add a description and some Redux woes
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