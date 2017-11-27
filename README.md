# Front-end Styleguide 

## Beginners Training

- [Introduction to Ember.js](https://teamgaslight.com/training/courses/14-introduction-to-ember-js)
- [Ember Guides](https://guides.emberjs.com/v2.16.0/)

## Core concepts

### DDAU - Unidirectional Data Flow

What Flux calls the "unidirectional data flow" is what we call "Data down, actions up" (DDAU) in Ember.

In the DDAU pattern, data flows one-way and there are no two-way bindings. Different parts of your application can remain highly decoupled and predictable, which means you will always know the source of an object's change. It's important to keep your components free from side effects.

![](https://i.imgur.com/A6gg5zA.png)

The DDAU are meant for `route -> component-container -> component` that are nested and follow a vertical structure.

Always follow DDAU. The idea is to avoid 2-way data binding. So data is mutated from:

`router -> component-container -> component1 -> ... -> componentN`

and actions go from:

`componentN -> ... -> component1 -> component-container -> router` <br><br>

https://emberway.io/skeleton-screen-loading-in-ember-js-2f7ac2384d63

Our components will be based on High order components and the idea of reuse. These two talks are prerequisites for the development of these components

- [Presentational and Container Components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)
- [Ember
Components](https://emberway.io/skeleton-screen-loading-in-ember-js-2f7ac2384d63)
- [Reusable Components](http://slides.com/miguelcamba/composable-components#/)
- [Higher Order Components](http://slides.com/miguelcamba/higher-order-components#/)

Here is an overview of our application’s data flow:<br><br>

![](https://emberigniter.com/images/start-here/graph.png)

Notice the uni-directional data flow. Data flows down (solid lines) and actions are sent up (dashed lines). Green lines are database calls. This approach is dubbed “Data Down, Actions Up” or DDAU for short.<br><br>


**One-way data bindings are the most idiomatic way of developing Ember applications**. In the spirit of React, this explicit data flow makes applications much easier to reason about and debug.

### Ember Components
Are based on of the [W3C Web Components specification](https://www.w3.org/TR/components-intro/). The specification is comprised of four smaller specifications; templates, decorators, shadow DOM, and custom elements. Of these four concepts only three of them have harden specifications, decorators being the exception. <br><br>

There are several important concepts to grasp when talking about components:<br><br>

 - Components know nothing about the outside world unless explicitly passed in
 - Components should have a well defined interface to the outside world
 - Components cannot manipulate any JavaScript outside of the component
 - Components can broadcast events
 - Custom elements must be namespaced with a hyphen
 - Outside JavaScript cannot manipulate components<br><br>

By dividing your code in small reusable chunks, you’re reducing complexity, by narrowing your focus into small bits at a time, you’re improving reusability, so that you don’t have to reinvent the wheel every time you want to reuse something, that you or someone else has already done.
So it seems like a great concept, to have a set of reusable components, that are tested and ready to use, that we can group together in order to create bigger ones, transforming them into fully functional web apps.<br><br>

Componentising our front end has some immediate major advantages, such as:<br><br>


 - **Consistency** - Implementing reusable components helps keep design consistent and can provide clarity in organising code.
 - **Maintainability** - A set of well organised components can be quick to update, and you can be more confident about which areas will and won't be affected.
 - **Scalability** - Having a library of components to implement can make for speedy development, and ensuring components are properly namespaced helps to avoid styles and functionality leaking into the wrong place as projects scale.<br><br>

> “Treat your code like Lego; many smaller, simpler chunks can be combined and arranged to make a huge variety of structures. With a box of assorted Lego pieces you could build a car, or an airplane, or the Eiffel Tower, or Big Ben, or anything! All by combining the same little tiny pieces in different quantities, in a different way, and in a different order.”
Nicolle Sullivan<br><br>


A closer look at the UI reveals the opportunity to group certain elements into basic components and compose those basic components into even bigger components.<br><br>

![](http://busypeoples.github.io/img/component_example.png)<br><br>

An Ember component consists of a Handlebars template file and an accompanying Ember class. The implementation of this class is required only if we need extra interactivity with the component. A component is usable in a similar manner to an ordinary HTML tag. When we build our tab switcher component, we will be able to use it like so:


```handlebars
{{#my-component}}{{/my-component}}
```
[Read more about ember components](https://guides.emberjs.com/v2.11.0/components/defining-a-component/)
<br><br>


### Coding style

* **eslint-plugin-ember.** we uses the [eslint-plugin-ember](https://github.com/ember-cli/eslint-plugin-ember) coding style.

* **ember test.** Before submitting a pull request.  check if all test pass.

* **Comments.** Include block-style (`/**`) comments before  functions with a non-trivial or non-obvious purpose. Include line-style (`//`) comments wherever code might not be obvious to a future contributor, years later, without your knowledge of the functioning of the code. If an intermediate-level Ember developer will wonder why something works, explain it.
* **Actions.** Accept action closures rather than strings representing action names.
`{{some-component someAction=(action "myAction")}}`, not `{{some-component someAction="myAction" param="the stuff" target=someTarget}}`. Invoke the action with `this.sendAction('onWhatever');`. There is no need to test for the presence of `onWhatever` as `sendAction` handles that situation.

* **indentation.** 2 spaces for JAVASCRIPT, HTML & CSS. Never tabs.

### Ember Testing

- [Ember Testing](https://guides.emberjs.com/v2.16.0/testing/)

- [Video Example](https://www.youtube.com/watch?v=2b1vcg_XSR8&t=541s)

- [Easy-Bake Testing]( https://www.slideshare.net/LizBaillie/easybake-testing-emberconf-2016)

### Ember style

- [Ember.js Dockyard](https://github.com/DockYard/styleguides/blob/master/engineering/ember.md)

- [Ember.js Styleguide](https://github.com/netguru/ember-styleguide)

- [Ember Components](https://poteto.github.io/component-best-practices/)

- [Ember Addon - Living Styleguide](https://github.com/chrislopresto/ember-freestyle)

### CSS style

- [Airbnb CSS](https://github.com/airbnb/css)

- [CSS Architecture](https://flama.github.io/css-styleguide/contents/stylesheets-folder-architecture)

- [RSCSS](http://rscss.io/index.html)
