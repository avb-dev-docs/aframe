---
title: Entity Component System
section_title: Introduction
type: introduction
layout: docs
parent_section: introduction
order: 2
section_order: 2
---

[entity]: ./entity.md
[component]: ./component.md
[system]: ./systems.md

A-Frame is built upon the **Entity-Component-System (ECS)** architectural pattern. ECS is a common pattern in game development that prioritizes composition over inheritance. In A-Frame, ECS allows developers to create complex 3D scenes by composing entities with reusable components and systems that provide global scope, services, and management to classes of components.

## Core Concepts

ECS revolves around three core concepts:

*   **Entities:** Entities are the fundamental building blocks of an A-Frame scene. They are essentially placeholders or containers to which we attach components. In A-Frame, an entity is represented by the `<a-entity>` HTML element. An entity itself doesn't do anything without components.

*   **Components:** Components are reusable modules of data that define the appearance, behavior, and functionality of an entity. A single entity can have multiple components, and components can be shared between entities. For example, a geometry component defines the shape of an entity, while a material component defines its appearance (color, texture).

*   **Systems:** Systems provide global scope and services to components. Systems manage and operate on groups of entities that share specific components. For example, a physics system might handle the movement and collision detection for all entities with a physics component.

## Relationship

The relationship between the three is that Entities hold Components. Systems act on entities that possess certain components.

## Benefits of ECS

Using ECS in A-Frame offers several benefits:

*   **Modularity:** Components are self-contained and reusable, making it easy to create and maintain complex scenes.

*   **Flexibility:** ECS allows you to easily combine different components to create unique and customized entities.

*   **Performance:** ECS promotes data locality, which can improve performance by reducing cache misses.

*   **Testability:** Each component can be tested independently, making it easier to ensure the quality of your code.

## Example

Consider a simple A-Frame scene with a red box:

```html
<a-scene>
  <a-entity geometry="primitive: box" material="color: red" position="0 1 -5"></a-entity>
</a-scene>
```

In this example:

*   `<a-entity>` is an entity.
*   `geometry="primitive: box"` is a component that defines the shape of the entity as a box.
*   `material="color: red"` is a component that defines the appearance of the entity as red.
* `position="0 1 -5"` is a component that defines the position of the entity in the 3D space.

## ECS in JavaScript

While A-Frame encourages declarative HTML, you can also interact with the ECS via JavaScript.

### Registering Components

You can register your own components using `AFRAME.registerComponent()`:

```js
AFRAME.registerComponent('my-component', {
  schema: {
    message: {type: 'string', default: 'Hello, A-Frame!'}
  },
  init: function () {
    console.log(this.data.message);
  }
});
```

### Accessing Components

You can access components on an entity using the `.components` property:

```js
var entity = document.querySelector('a-entity');
var myComponent = entity.components['my-component'];
console.log(myComponent.data.message);
```

### Working with Systems

You can also access a system using `document.querySelector('a-scene').systems[systemName];`.

```js
var mySystem = document.querySelector('a-scene').systems['my-system'];
```

## Further Reading

*   [Entity][entity]
*   [Component][component]
*   [System][system]