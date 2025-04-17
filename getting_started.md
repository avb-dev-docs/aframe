```markdown
---
title: Getting Started with A-Frame
description: A comprehensive guide to get started with A-Frame, covering installation, scene setup, basic shapes, and a simple example.
---

# Getting Started with A-Frame

A-Frame is a web framework for building virtual reality (VR) experiences. A-Frame is based on top of HTML, making it easy to get started. This guide will walk you through setting up A-Frame, creating a basic scene, adding primitive shapes, and running a simple example.

## Installation

The easiest way to get started with A-Frame is to include the A-Frame library from a CDN in your HTML file:

```html
<head>
  <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
</head>
```

Alternatively, you can install A-Frame via npm or yarn for local development:

```sh
npm install aframe
# or
yarn add aframe
```

Then, import A-Frame into your JavaScript file:

```js
import AFRAME from 'aframe';
```

## Basic Scene Setup

An A-Frame scene is created using the `<a-scene>` element. This element initializes the VR environment and handles rendering.  Within the `<a-scene>`, you add entities using the `<a-entity>` element.  Entities are containers for components, which define the appearance and behavior of objects in the scene.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My First A-Frame Scene</title>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <!-- 3D content here -->
    </a-scene>
  </body>
</html>
```

## Adding Basic Shapes

A-Frame provides several built-in primitive shapes that you can easily add to your scene. These include:

*   **`<a-box>`**: A cube.
*   **`<a-sphere>`**: A sphere.
*   **`<a-cylinder>`**: A cylinder.
*   **`<a-plane>`**: A flat plane.
*   **`<a-sky>`**: A background.

To add a shape, simply include its corresponding element within the `<a-scene>`. You can then customize its appearance and position using attributes.  Common attributes include `position`, `rotation`, `scale`, and `color`.

```html
<a-scene>
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```

*   **position**: Specifies the x, y, and z coordinates of the object.
*   **rotation**: Specifies the rotation of the object in degrees around the x, y, and z axes.
*   **scale**: Specifies the scaling factor of the object along the x, y, and z axes.
*   **color**: Specifies the color of the object using a hexadecimal color code or a color name.

## Simple Example Project

Here's a complete example that creates a scene with a box, sphere, cylinder, plane, and sky:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>A-Frame Basic Scene</title>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene background="color: #ECECEC">
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9" shadow></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" shadow></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D" shadow></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow></a-plane>
      <a-sky color="#ECECEC"></a-sky>
    </a-scene>
  </body>
</html>
```

Save this code as an HTML file (e.g., `index.html`) and open it in your browser. You should see a simple VR scene with several basic shapes. If you have a VR headset, you can view the scene in VR mode. If not, you can still navigate the scene using your mouse and keyboard.

## Next Steps

This guide provides a basic introduction to A-Frame.  To learn more, explore the following resources:

*   [A-Frame Documentation](https://aframe.io/docs/1.7.1/introduction/): The official A-Frame documentation provides comprehensive information on all aspects of the framework.
*   [A-Frame Examples](https://aframe.io/aframe/examples/): A collection of A-Frame examples demonstrating various features and techniques.
*   [A-Frame School](https://aframe.io/school/): A series of tutorials that teach you how to build VR experiences with A-Frame.
*   [A-Frame Community](https://aframe.io/community/): Connect with other A-Frame developers and enthusiasts.
```