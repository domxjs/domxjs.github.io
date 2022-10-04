---
layout: page
title: Data Elements
permalink: /data-elements
githuburl: https://github.com/domxjs/domx/tree/master/packages/DataElement
---
# Data Elements

## Description
The `DataElement` base class provides for a Flux/Redux style unidirectional data flow state management
pattern using DOM events and custom elements.

By utilizing the DOM and custom elements, the footprint is small and 
performance is fast since communication happens through
DOM events and not a JavaScript library.

It works well with `LitElement` since that also uses custom elements,
but since it is a custom element itself, it will work with any (or no)
library/framework.

See: <a href="/state-management">State Management</a>


## Basic Usage
This is a contrived example showing default usage of a `DataElement`;

```js
import { customDataElement, DataElement, event } from "@domx/dataelement";

@customDataElement("session-data", {
    eventsListenAt: "window"
});
export class SessionData extends DataElement {
    static defaultState = {
        loggedInUserName: "",
        loggedInUsersFullName: ""
    };

    state = SessionData.defaultState;

    // event creator
    static userLoggedInEvent = (userName, fullName) => 
        new CustomEvent("user-logged-in", {
            bubbles: true,
            composed: true,
            detail: {userName, fullName}
        });

    @event("user-logged-in")
    userLoggedIn({detail:{userName, fullName}}) {
        this.state = {
            ...this.state,
            loggedInUserName: userName,
            loggedInUsersFullName: fullName
        };
        this.dispatchEvent(new CustomEvent("state-changed"));
    }
}
```

### UI Component
## Basic Usage
This is a contrived example showing default usage of a DataElement.

```js
import { DataElement } from "@domx/dataelement";
import { customDataElement, event } from "@domx/dataelement/decorators";


export class UserLoggedInEvent extends Event {
    static eventType = "user-logged-in";
    userName:string;
    fullName:string;
    constructor(userName:string, fullName:string) {
        super(UserLoggedInEvent.eventType, {
            bubbles: true,
            composed: true
        });
        this.userName = userName;
        this.fullName = fullName;
    }
}


@customDataElement("session-data", {
    eventsListenAt: "window"
});
export class SessionData extends DataElement {
    static defaultState = {
        loggedInUserName: "",
        loggedInUsersFullName: ""
    };

    state = SessionData.defaultState;

    // event comes from the EventMap package
    @event(UserLoggedInEvent.eventType)
    userLoggedIn(event:UserLoggedInEvent) {
        this.state = {
            ...this.state,
            loggedInUserName: event.userName,
            loggedInUsersFullName: event.fullName
        };
        this.dispatchEvent(new Event("state-changed"));
    }
}
```
> By subclassing the Event class, The `UserLoggedInEvent` acts 
as a great way to document what events a data element can handle.
This is similar to action creators in Redux. They can be defined
in the same file as the DataElement (or in a separate file
if that works better for you) and used by UI components
to trigger events.

> The static `defaultState` property allows UI components
to reference the `defaultState` for initialization.

### UI Component
The `SessionData` element can be used in any UI component.

```js
import { LitElement, html } from "lit";
import { customElement } from "lit/decorators.js";
import { linkProp } from "@domx/dataelement";
import { SessionData, UserLoggedInEvent } from "./SessionData";

class LoggedInUser extends LitElement {
    state = SessionData.defaultState;

    render() {
        const state = this.state;

        return html`
            <session-data
                @state-changed="${linkProp(this, "state")}"
            ></session-data>
            <button @click="${this.updateUserClicked}">Update user</button>
            <div>
                Logged in as: ${state.loggedInUserName}
                (${state.loggedInUsersFullName})
            </div>
        `;
    }
    
    updateUserClicked(event) {
        this.dispatchEvent(new UserLoggedInEvent("juser", "Joe User"));
    }
}
```
> linkProp is a helper method to propagate changes from a data element to its
parent UI element. See [linkProp](https://github.com/domxjs/domx/tree/master/packages/linkProp).


## Highlights
- Works with Redux Dev Tools.
- Can configure any (and multiple) properties to be a `state` property.
- Can use/configure a `stateId` property to track state for instance data.
- Works with (but does not require) the [StateChange](https://github.com/domxjs/domx/tree/master/packages/StateChange) monad for `functional` JavaScript patterns (e.g. `reducers`)
  - `StateChange` also works with [Immer](https://github.com/immerjs/immer) which
  eliminates object creation fatigue when working with immutable state.
- Uses [EventMap](https://github.com/domxjs/domx/tree/master/packages/EventMap)
for declarative DOM event handling on custom elements.
- Top question: "can it really be that simple?"
