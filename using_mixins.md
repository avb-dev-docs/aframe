```markdown
---
title: Using Mixins
description: Learn how to use mixins in A-Frame to create reusable sets of component properties.
---

# Using Mixins

Mixins in A-Frame provide a way to define reusable sets of component properties. This allows you to apply the same configuration to multiple entities, reducing redundancy and improving code maintainability. Mixins are defined using the `<a-mixin>` element and applied to entities using the `mixin` attribute.

## Defining a Mixin

To define a mixin, use the `<a-mixin>` element within the `<a-scene>` element.  The `id` attribute of the `<a-mixin>` element is used to identify the mixin.  Specify the component properties within the `<a-mixin>` element as attributes, just like on a regular entity.

```html
<a-scene>
  <a-mixin id="red-cube" color="red" geometry="primitive: box"></a-mixin>
  <!-- ... -->
</a-scene>
```

In the example above, we define a mixin with the `id` "red-cube".  This mixin sets the `color` component to "red" and the `geometry` component to a box.

## Applying a Mixin to an Entity

To apply a mixin to an entity, use the `mixin` attribute on the entity.  The value of the `mixin` attribute should be the `id` of the mixin you want to apply.  You can specify multiple mixins by separating their IDs with spaces.

```html
<a-scene>
  <a-mixin id="red-cube" color="red" geometry="primitive: box"></a-mixin>
  <a-entity mixin="red-cube" position="0 1 0"></a-entity>
  <!-- ... -->
</a-scene>
```

In this example, the `a-entity` will inherit the `color` and `geometry` properties from the "red-cube" mixin.  The `a-entity` will render a red box at position (0, 1, 0).

## Multiple Mixins

You can apply multiple mixins to a single entity.  When multiple mixins define the same component property, the mixin that appears last in the `mixin` attribute will take precedence. Component properties defined directly on the entity will always override mixin values.

```html
<a-scene>
  <a-mixin id="red" color="red"></a-mixin>
  <a-mixin id="cube" geometry="primitive: box"></a-mixin>
  <a-entity mixin="red cube" position="0 1 0"></a-entity>
  <a-entity mixin="cube red" position="1 1 0"></a-entity>
</a-scene>
```

In this example, the first entity will be a red cube and the second entity will also be a red cube (order doesn't matter).

## Overriding Mixin Properties

You can override mixin properties by setting the corresponding attribute directly on the entity.

```html
<a-scene>
  <a-mixin id="red-cube" color="red" geometry="primitive: box"></a-mixin>
  <a-entity mixin="red-cube" color="blue" position="0 1 0"></a-entity>
</a-scene>
```

In this example, the `a-entity` will render a *blue* box, because the `color` attribute is set directly on the entity, overriding the `color` defined in the "red-cube" mixin.

## Dynamic Updates

When a mixin is updated, all entities that use the mixin will automatically update to reflect the changes. This allows you to easily modify the properties of multiple entities at once.

```html
<a-scene>
  <a-mixin id="my-mixin" color="red"></a-mixin>
  <a-entity mixin="my-mixin"></a-entity>

  <script>
    setTimeout(() => {
      const mixinEl = document.querySelector('#my-mixin');
      mixinEl.setAttribute('color', 'green');
    }, 2000);
  </script>
</a-scene>
```

In the above example, the entity will initially be red. After 2 seconds, a script updates the color attribute of the mixin to green, and the entity will automatically change to green.

## Caching

A-Frame caches mixin attributes when the mixin and entity are loaded.  The `cacheAttribute` function in `a-mixin.js` handles this caching, and mixins use `parseComponentAttrValue` to ensure values are parsed correctly before being cached. If you modify attributes from JS or other means, make sure to call `.flushToDOM()` if the properties are not updating

## When Mixins Load

Entities are updated when a mixin is attached via `updateEntities`. The `doConnectedCallback` handles the initial cache and update and the `attributeChangedCallback` handles subsequent updates.

```javascript
 entity.mixinUpdate(this.id);
```