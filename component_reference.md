```markdown
---
title: Component Reference
type: reference
layout: docs
parent_section: components
order: 1
---

This page provides a detailed API reference for all built-in A-Frame components, organized by category.

<!--toc-->

## Geometry Components

Geometry components define the shape of an entity.

### box Component

The `box` component creates a rectangular box.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| width    | number | 1       | Width of the box in meters.                |
| height   | number | 1       | Height of the box in meters.               |
| depth    | number | 1       | Depth of the box in meters.                |
| segmentsWidth | int | 1 | Number of width segments. |
| segmentsHeight | int | 1 | Number of height segments. |
| segmentsDepth | int | 1 | Number of depth segments. |

**Example:**

```html
<a-entity geometry="primitive: box; width: 2; height: 0.5; depth: 1"></a-entity>
```

### circle Component

The `circle` component creates a flat circle or cylinder.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radius   | number | 1       | Radius of the circle in meters.              |
| segments | int    | 32      | Number of segments in the circle.            |
| thetaStart | number | 0       | Starting angle for first segment, in radians. |
| thetaLength | number | 360       | The central angle, often called theta, of the circular sector. The default is 360, which makes for a complete circle. |

**Example:**

```html
<a-entity geometry="primitive: circle; radius: 0.75; segments: 64"></a-entity>
```

### cone Component

The `cone` component creates a cone.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radiusBottom | number | 1       | Radius of the bottom of the cone in meters.   |
| radiusTop   | number | 0       | Radius of the top of the cone in meters.   |
| height   | number | 1       | Height of the cone in meters.              |
| segmentsRadial | int    | 36      | Number of segments around the radial circumference of the cone.            |
| segmentsHeight | int    | 1       | Number of segments along the height of the cone.            |
| openEnded | boolean | false | A Boolean indicating whether the base of the cone is open or not. |
| thetaStart | number | 0       | Starting angle for first segment, in radians. |
| thetaLength | number | 360       | The central angle, often called theta, of the circular sector. The default is 360, which makes for a complete circle. |

**Example:**

```html
<a-entity geometry="primitive: cone; radiusBottom: 0.5; height: 1"></a-entity>
```

### cylinder Component

The `cylinder` component creates a cylinder.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radius   | number | 1       | Radius of the cylinder in meters.              |
| height   | number | 1       | Height of the cylinder in meters.               |
| segmentsRadial | int    | 36      | Number of segments around the radial circumference of the cylinder.            |
| segmentsHeight | int    | 1       | Number of segments along the height of the cylinder.            |
| openEnded | boolean | false | A Boolean indicating whether the base of the cylinder is open or not. |
| thetaStart | number | 0       | Starting angle for first segment, in radians. |
| thetaLength | number | 360       | The central angle, often called theta, of the circular sector. The default is 360, which makes for a complete circle. |

**Example:**

```html
<a-entity geometry="primitive: cylinder; radius: 0.5; height: 2"></a-entity>
```

### plane Component

The `plane` component creates a flat plane.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| width    | number | 1       | Width of the plane in meters.                |
| height   | number | 1       | Height of the plane in meters.               |
| segmentsWidth | int | 1 | Number of width segments. |
| segmentsHeight | int | 1 | Number of height segments. |

**Example:**

```html
<a-entity geometry="primitive: plane; width: 3; height: 2"></a-entity>
```

### ring Component

The `ring` component creates a flat ring or torus section.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radiusInner   | number | 0.5       | The inner radius of the torus.                 |
| radiusOuter    | number | 1       | The outer radius of the torus.               |
| segmentsTheta | int | 32 | Number of segments per whole circle. |
| segmentsPhi | int | 8 | Number of segments along the radius from the interior to the exterior of the ring. |
| thetaStart | number | 0       | Starting angle for first segment, in radians. |
| thetaLength | number | 360       | The central angle, often called theta, of the circular sector. The default is 360, which makes for a complete circle. |

**Example:**

```html
<a-entity geometry="primitive: ring; radiusInner: 0.4; radiusOuter: 1"></a-entity>
```

### sphere Component

The `sphere` component creates a sphere.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radius   | number | 1       | Radius of the sphere in meters.              |
| segmentsWidth | int | 32 | Number of horizontal segments. |
| segmentsHeight | int | 16 | Number of vertical segments. |
| phiStart | number | 0 | Specifies how much of the horizontal circumference the sphere has. |
| phiLength | number | 360 | Specifies how much of the horizontal circumference the sphere has. |
| thetaStart | number | 0 | Specifies how much of the vertical circumference the sphere has. |
| thetaLength | number | 180 | Specifies how much of the vertical circumference the sphere has. |

**Example:**

```html
<a-entity geometry="primitive: sphere; radius: 1.5; segmentsWidth: 64; segmentsHeight: 32"></a-entity>
```

### torus Component

The `torus` component creates a torus.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radius   | number | 1       | Radius of the entire torus.              |
| radiusTubular | number | 0.2 | Radius of the tube. |
| segmentsRadial | int | 32 | Number of segments around the circle forming the tube. |
| segmentsTubular | int | 36 | Number of segments along the circumference of the tube. |
| arc | number | 360 | Central angle or arc length in radians. |

**Example:**

```html
<a-entity geometry="primitive: torus; radius: 2; radiusTubular: 0.5"></a-entity>
```

### torusKnot Component

The `torusKnot` component creates a torus knot.

| Property | Type   | Default | Description                                  |
| -------- | ------ | ------- | -------------------------------------------- |
| radius   | number | 1       | Radius of the entire torus.              |
| radiusTubular | number | 0.2 | Radius of the tube. |
| segmentsRadial | int | 64 | Number of segments along the radius of the tube. |
| segmentsTubular | int | 8 | Number of segments along the circumference of the tube. |
| p | int | 2 | How many times the geometry winds around its axis of rotational symmetry. |
| q | int | 3 | How many times the geometry winds around a circle in the interior of the torus. |

**Example:**

```html
<a-entity geometry="primitive: torusKnot; radius: 1.5; radiusTubular: 0.3"></a-entity>
```

### Buffer Geometry Component

For advanced usage, you can also specify a custom buffer geometry. This is generally not done via the geometry component, instead you should create your own component that creates a `THREE.BufferGeometry` and sets it on the entity.

## Material Components

Material components define the appearance of an entity.

### material Component

The `material` component defines the basic visual properties of an entity.

| Property         | Type    | Default | Description                                                                 |
| ---------------- | ------- | ------- | --------------------------------------------------------------------------- |
| color            | color   | #FFF    | The color of the material.                                                |
| shader           | string  | standard| The type of shader used to render the material (standard, flat, matcap).       |
| src              | asset   |         | Path to a texture.                                                        |
| normalMap        | asset   |         | Path to a normal map texture.                                             |
| roughness        | number  | 0.5     | How rough the material is.                                                  |
| metalness        | number  | 0.5     | How metallic the material is.                                                |
| transparent      | boolean | false   | Whether the material is transparent.                                        |
| opacity          | number  | 1       | The opacity of the material (0 to 1).                                      |
| side             | string  | front   | Which side of the material to render (front, back, double).                |
| emissive         | color   | #000     | Emissive color of the material.                                             |
| emissiveIntensity| number  | 1       | Intensity of the emissive color.                                            |
| ambientOcclusionTexture | asset | | Sets the ambient occlusion map. |
| alphaTest | number | 0 | Defines how alpha is used to determine what is visible. |
| displacementBias | number | 0 | The offset of the displacement map. |
| displacementScale | number | 1 | How much the displacement map affects the geometry. |
| displacementMap | asset | | The texture used for displacement mapping. |
| envMap | asset | | The environment map. |
| fog | boolean | true | Define whether the material is affected by fog. |
| lightMap | asset | | Sets the light map. |
| normalScale | vec2 | {x: 1, y: 1} | How much the normal map affects the material. |
| repeat | vec2 | {x: 1, y: 1} | How many times the texture repeats across the surface. |
| shininess | number | 30 | How shiny the specular highlight is. |
| sphericalEnvMap | asset | | The spherical environment map. |
| wireframe | boolean | false | Render geometry as wireframe. |
| wireframeLinewidth | number | 1 | Line width of the wireframe. |

**Example:**

```html
<a-entity geometry="primitive: box" material="color: blue; roughness: 0.8"></a-entity>
```

### shader: flat

A simple shader that renders the material with a single color, without lighting.

```html
<a-entity geometry="primitive: box" material="shader: flat; color: green"></a-entity>
```

### shader: matcap

A shader that renders the material using a MatCap (Material Capture) texture.

```html
<a-entity geometry="primitive: sphere" material="shader: matcap; matcap: url(path/to/matcap.png)"></a-entity>
```

* matcap (asset) - Path to the MatCap texture.

## Light Components

Light components add lighting to the scene.

### light Component

The `light` component adds a light source to the entity.

| Property | Type    | Default | Description                                                                 |
| -------- | ------- | ------- | --------------------------------------------------------------------------- |
| type     | string  | directional | The type of light (directional, point, spot, ambient, hemisphere).        |
| color    | color   | #FFF    | The color of the light.                                                   |
| intensity| number  | 1       | The intensity of the light.                                                 |
| distance | number  | 0       | Maximum range of the light.                                                 |
| decay    | number  | 1       | The amount the light dims along the distance of the light.                   |
| angle    | number  | PI/6    | Maximum angle of light dispersion from its direction (spot lights only).   |
| penumbra | number  | 0       | Percent of the spotlight cone that is attenuated from the edge (spot lights only). |
| shadow   | boolean | false   | Whether the light casts shadows.                                           |
| shadowBias | number | 0 | How much the shadows will deviate from the light. |
| shadowMapWidth | number | 512 | Width of the shadow map. |
| shadowMapHeight | number | 512 | Height of the shadow map. |
| shadowRadius | number | 1 | Radius of the shadows. |

**Example:**

```html
<a-entity light="type: point; color: yellow; intensity: 0.8"></a-entity>
```

### type: ambient

Creates an ambient light. This light globally illuminates all objects in the scene equally. Ambient lights cannot be used to cast shadows as they do not have a direction.

### type: directional

Creates a directional light. Directional lights are similar to sunlight; they illuminate all objects equally from a specific direction. Directional lights can be used to cast shadows.

### type: hemisphere

Creates a hemisphere light. A hemisphere light is positioned directly above the scene, with color fading from the sky color to the ground color.

*   groundColor (color) - The color coming from the ground. Default is #000.
*   skyColor (color) - The color coming from the sky. Default is #FFF.

### type: point

Creates a point light. Point lights emit light in all directions from a single point. Point lights can be used to cast shadows.

### type: spot

Creates a spot light. Spot lights emit light from a single point in a specific direction. Spot lights can be used to cast shadows.

## Camera Components

Camera components define the viewpoint of the scene.

### camera Component

The `camera` component defines the camera used to render the scene.

| Property | Type    | Default | Description                                                                 |
| -------- | ------- | ------- | --------------------------------------------------------------------------- |
| active    | boolean | true    | Whether the camera is active.                                               |
| far      | number  | 1000    | The far clipping plane.                                                      |
| fov      | number  | 80      | The field of view in degrees.                                               |
| near     | number  | 0.5     | The near clipping plane.                                                     |
| zoom     | number  | 1       | The zoom factor.                                                            |
| userHeight | number  | 1.6     | The default user height.                                                            |

**Example:**

```html
<a-entity camera look-controls wasd-controls></a-entity>
```

## Core Components

These components are fundamental to A-Frame and are often used in conjunction with other components.

### position Component

The `position` component defines the entity's position in 3D space.

| Property | Type | Default    | Description                                                                    |
| -------- | ---- | ---------- | ------------------------------------------------------------------------------ |
| x        | number | 0          | The X coordinate of the position.                                             |
| y        | number | 0          | The Y coordinate of the position.                                             |
| z        | number | 0          | The Z coordinate of the position.                                             |

**Example:**

```html
<a-entity position="1 2 -3"></a-entity>
```

### rotation Component

The `rotation` component defines the entity's rotation in 3D space (degrees).

| Property | Type | Default    | Description                                                                    |
| -------- | ---- | ---------- | ------------------------------------------------------------------------------ |
| x        | number | 0          | The X component of the rotation (pitch).                                             |
| y        | number | 0          | The Y component of the rotation (yaw).                                             |
| z        | number | 0          | The Z component of the rotation (roll).                                             |

**Example:**

```html
<a-entity rotation="45 90 0"></a-entity>
```

### scale Component

The `scale` component defines the entity's scale in 3D space.

| Property | Type | Default    | Description                                                                    |
| -------- | ---- | ---------- | ------------------------------------------------------------------------------ |
| x        | number | 1          | The X component of the scale.                                             |
| y        | number | 1          | The Y component of the scale.                                             |
| z        | number | 1          | The Z component of the scale.                                             |

**Example:**

```html
<a-entity scale="0.5 0.5 0.5"></a-entity>
```

### visible Component

The `visible` component defines whether the entity is visible.

| Property | Type    | Default | Description                                                                 |
| -------- | ------- | ------- | --------------------------------------------------------------------------- |
| visible  | boolean | true    | Whether the entity is visible.                                               |

**Example:**

```html
<a-entity visible="false"></a-entity>
```

## Control Components

These components add interactivity to the scene.

### look-controls Component

The `look-controls` component enables mouse or touch-based camera rotation.

| Property | Type    | Default | Description                                                                 |
| -------- | ------- | ------- | --------------------------------------------------------------------------- |
| pointerLockEnabled  | boolean | false | To enable pointer lock on desktop devices. |
| magicWindowTrackingEnabled | boolean | true | Whether or not to use magic window tracking. |

**Example:**

```html
<a-entity camera look-controls></a-entity>
```

### wasd-controls Component

The `wasd-controls` component enables keyboard-based camera movement.

| Property | Type    | Default | Description                                                                 |
| -------- | ------- | ------- | --------------------------------------------------------------------------- |
| acceleration | number | 60 | The rate (in m/s^2) at which the entity accelerates when moving. |
| adAxis | string | x | Axis which the A and D keys rotate around. |
| enabled | boolean | true | Enable or disable controls. |
| fly | boolean | false | Let the camera fly, do not constrain to the XZ plane. |
| gamepadEnabled | boolean | true | Enable or disable gamepad input. |
| keyboardEnabled | boolean | true | Enable or disable keyboard input. |
| lookSpeed | number | 0.05 | Camera rotation speed when using the keyboard. |
| maxSpeed | number | 1.6 | Maximum speed (in m/s) the entity can travel at. |
| moveXAxis | string | x | Axis which the W and S keys move along. |
| moveYAxis | string | y | Axis which the Q and E keys move along. |
| moveZAxis | string | z | Axis which the A and D keys move along. |
| rotateSpeed | number | 0.05 | Camera rotation speed when using the keyboard. |
| wasdAxis | string | z | Axis which the W and S keys move along. |
| wasdEnabled | boolean | true | Enable or disable WASD input. |

**Example:**

```html
<a-entity camera wasd-controls></a-entity>
```

## Scene Components

These components modify the entire scene.

### background Component

The `background` component sets the background color or a static equirectangular image.

| Property | Type | Default | Description |
|---|---|---|---|
| color | color | #fff | The background color, applied if src is not set. |
| src | asset | null | Path to the equirectangular image to be displayed as the background. |

**Example:**

```html
<a-scene background="color: #24CAFF"></a-scene>

<a-scene background="src: url(path/to/image.jpg)"></a-scene>
```

### fog Component

The `fog` component sets the fog properties for the scene.

| Property | Type | Default | Description |
|---|---|---|---|
| color | color | #000000 | The color of the fog. |
| near | number | 1 | All objects closer than near to the camera will not be affected by the fog. |
| far | number | 1000 | All objects farther than far from the camera will be entirely affected by the fog. |
| density | number | 0.00025 | How the density of the fog changes with distance. |

**Example:**

```html
<a-scene fog="color: #AAA; near: 0.05; far: 16"></a-scene>
```

This is a subset of A-Frame's components. More components will be added.
```