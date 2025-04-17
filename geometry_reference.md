```markdown
---
title: Geometry Reference
type: docs
layout: docs
parent_section: docs
section_title: Components
section_order: 5
---

This page provides a comprehensive reference for all built-in geometries supported by A-Frame.

<!--toc-->

## Built-in Geometries

### `box`

The `box` geometry defines boxes (i.e., any quadrilateral, not just cubes).

```html
<a-entity geometry="primitive: box; width: 1; height: 1; depth: 1"></a-entity>
```

| Property       | Description                                    | Type   | Default Value |
|----------------|------------------------------------------------|--------|---------------|
| width          | Width (in meters) of the sides on the X axis.  | number | 1             |
| height         | Height (in meters) of the sides on the Y axis. | number | 1             |
| depth          | Depth (in meters) of the sides on the Z axis.  | number | 1             |
| segmentsDepth  | Number of segmented faces on the z-axis        | int    | 1             |
| segmentsHeight | Number of segmented faces on the y-axis        | int    | 1             |
| segmentsWidth  | Number of segmented faces on the x-axis        | int    | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: box; width: 2; height: 0.5; depth: 3" material="color: red"></a-entity>
</a-scene>
```

### `circle`

The `circle` geometry creates flat two-dimensional circles. These can be complete circles or partial circles (like Pac-Man). Note that because circles are flat, A-Frame will only render a single face of the circle if we don't specify `side: double` on the `material` component.

```html
<a-entity geometry="primitive: circle; radius: 1" material="side: double"></a-entity>
```

| Property    | Description                                                                                                                      | Type   | Default Value |
|-------------|----------------------------------------------------------------------------------------------------------------------------------|--------|---------------|
| radius      | Radius (in meters) of the circle.                                                                                                | number | 1             |
| segments    | Number of triangles to construct the circle, like pizza slices. A higher number of segments means the circle will be more round. | int    | 32            |
| thetaStart  | Start angle for first segment. Can be used to define a partial circle.                                                           | number | 0             |
| thetaLength | The central angle (in degrees). Defaults to `360`, which makes for a complete circle.                                            | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: circle; radius: 2; segments: 64" material="color: blue; side: double"></a-entity>
  <a-entity geometry="primitive: circle; radius: 1; thetaStart: 45; thetaLength: 90" material="color: green; side: double" position="0 1 0"></a-entity>
</a-scene>
```

### `cone`

The `cone` geometry is a cylinder geometry that has different top and bottom radii.

```html
<a-entity geometry="primitive: cone; radiusBottom: 1; radiusTop: 0.1"></a-entity>
```

| Property       | Description                                                     | Type   | Default Value |
|----------------|-----------------------------------------------------------------|--------|---------------|
| height         | Height of the cone.                                             | number | 2             |
| openEnded      | Whether the ends of the cone are open (true) or capped (false). | bool   | false         |
| radiusBottom   | Radius of the bottom end of the cone.                           | number | 1             |
| radiusTop      | Radius of the top end of the cone.                              | number | 1             |
| segmentsRadial | Number of segmented faces around the circumference of the cone. | int    | 36            |
| segmentsHeight | Number of rows of faces along the height of the cone.           | int    | 18            |
| thetaStart     | Starting angle in degrees.                                      | number | 0             |
| thetaLength    | Central angle in degrees.                                       | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: cone; radiusBottom: 0.5; radiusTop: 0; height: 1" material="color: orange"></a-entity>
</a-scene>
```

### `cylinder`

The `cylinder` geometry creates cylinders in the traditional sense, but it can also define shapes such as tubes and curved surfaces.

```html
<a-entity geometry="primitive: cylinder; height: 3; radius: 2"></a-entity>
```

| Property       | Description                                                         | Type   | Default Value |
|----------------|---------------------------------------------------------------------|--------|---------------|
| radius         | Radius of the cylinder.                                             | number | 1             |
| height         | Height of the cylinder.                                             | number | 2             |
| segmentsRadial | Number of segmented faces around the circumference of the cylinder. | int    | 36            |
| segmentsHeight | Number of rows of faces along the height of the cylinder.           | int    | 18            |
| openEnded      | Whether the ends of the cylinder are open (true) or capped (false). | bool   | false         |
| thetaStart     | Starting angle in degrees.                                          | number | 0             |
| thetaLength    | Central angle in degrees.                                           | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: cylinder; radius: 0.5; height: 2; segmentsRadial: 12" material="color: purple"></a-entity>
</a-scene>
```

### `dodecahedron`

The `dodecahedron` geometry creates a polygon with twelve equally-sized faces.

```html
<a-entity geometry="primitive: dodecahedron; radius: 2"></a-entity>
```

| Property | Description                             | Type   | Default Value |
|----------|-----------------------------------------|--------|---------------|
| radius   | Radius (in meters) of the dodecahedron. | number | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: dodecahedron; radius: 0.75" material="color: teal"></a-entity>
</a-scene>
```

### `icosahedron`

The `icosahedron` geometry creates a polygon with twenty equilateral triangular faces.

```html
<a-entity geometry="primitive: icosahedron"></a-entity>
```

| Property | Description                            | Type   | Default Value |
|----------|----------------------------------------|--------|---------------|
| radius   | Radius (in meters) of the icosahedron. | number | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: icosahedron; radius: 0.75" material="color: lightblue"></a-entity>
</a-scene>
```

### `octahedron`

The `octahedron` geometry creates a polygon with eight equilateral triangular faces.

```html
<a-entity geometry="primitive: octahedron"></a-entity>
```

| Property | Description                            | Type   | Default Value |
|----------|----------------------------------------|--------|---------------|
| radius   | Radius (in meters) of the octahedron. | number | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: octahedron; radius: 0.75" material="color: limegreen"></a-entity>
</a-scene>
```

### `plane`

The `plane` geometry creates a flat surface. Because planes are flat, A-Frame will render only a single face of the plane unless we specify `side: double` on the `material` component.

```html
<a-entity geometry="primitive: plane; height: 10; width: 10" material="side: double"></a-entity>
```

| Property       | Description                             | Type   | Default Value |
|----------------|-----------------------------------------|--------|---------------|
| width          | Width along the X axis.                 | number | 1             |
| height         | Height along the Y axis.                | number | 1             |
| segmentsHeight | Number of segmented faces on the y-axis | int    | 1             |
| segmentsWidth  | Number of segmented faces on the x-axis | int    | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: plane; width: 5; height: 5" material="color: gray; side: double"></a-entity>
</a-scene>
```

### `ring`

The `ring` geometry creates a flat ring. Because the ring is flat, A-Frame will only render a single face of the ring unless we specify `side: double` on the `material` component.

```html
<a-entity geometry="primitive: ring; radiusInner: 0.5; radiusOuter: 1" material="side: double"></a-entity>
```

| Property      | Description                                                            | Type   | Default Value |
|---------------|------------------------------------------------------------------------|--------|---------------|
| radiusInner   | Radius of the inner hole of the ring.                                  | number | 1             |
| radiusOuter   | Radius of the outer edge of the ring.                                  | number | 1             |
| segmentsTheta | Number of segments. A higher number means the ring will be more round. | int    | 32            |
| segmentsPhi   | Number of triangles within each face defined by segmentsTheta.         | int    | 8             |
| thetaStart    | Starting angle in degrees.                                             | number | 0             |
| thetaLength   | Central angle in degrees.                                              | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: ring; radiusInner: 0.4; radiusOuter: 1; segmentsTheta: 64" material="color: yellow; side: double"></a-entity>
</a-scene>
```

### `sphere`

The `sphere` geometry creates spheres.

```html
<a-entity geometry="primitive: sphere; radius: 2"></a-entity>
```

| Property       | Description                    | Type   | Default Value |
|----------------|--------------------------------|--------|---------------|
| radius         | Radius of the sphere.          | number | 1             |
| segmentsWidth  | Number of horizontal segments. | int    | 18            |
| segmentsHeight | Number of vertical segments.   | int    | 36            |
| phiStart       | Horizontal starting angle.     | number | 0             |
| phiLength      | Horizontal sweep angle size.   | number | 360           |
| thetaStart     | Vertical starting angle.       | number | 0             |
| thetaLength      | Vertical sweep angle size.     | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: sphere; radius: 0.75" material="color: lightgreen"></a-entity>
</a-scene>
```

### `tetrahedron`

The `tetrahedron` geometry creates a polygon with four triangular faces.

```html
<a-entity geometry="primitive: tetrahedron; radius: 2"></a-entity>
```

| Property | Description                                                                  | Type   | Default Value |
|----------|------------------------------------------------------------------------------|--------|---------------|
| radius   | Radius (in meters) of the tetrahedron.                                       | number | 1             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: tetrahedron; radius: 0.75" material="color: coral"></a-entity>
</a-scene>
```

### `torus`

The `torus` geometry creates a donut or curved tube shape.

```html
<a-entity geometry="primitive: torus; radius: 2; radiusTubular: 0.5; arc: 180"></a-entity>
```

| Property        | Description                                                                                                     | Type   | Default Value |
|-----------------|-----------------------------------------------------------------------------------------------------------------|--------|---------------|
| radius          | Radius of the outer edge of the torus.                                                                          | number | 1             |
| radiusTubular   | Radius of the tube.                                                                                             | number | 0.2           |
| segmentsRadial  | Number of segments along the circumference of the tube ends. A higher number means the tube will be more round. | int    | 36            |
| segmentsTubular | Number of segments along the circumference of the tube face. A higher number means the tube will be more round. | int    | 32            |
| arc             | Central angle.                                                                                                  | number | 360           |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: torus; radius: 1; radiusTubular: 0.3" material="color: pink"></a-entity>
</a-scene>
```

### `torusKnot`

The `torusKnot` geometry creates a pretzel shape. A pair of coprime integers, `p` and `q`, defines the particular shape of the pretzel. If `p` and `q` are not coprime the result will be a torus link.

```html
<a-entity geometry="primitive: torusKnot; p: 3; q:7"></a-entity>
```

| Property        | Description                                                                                                     | Type   | Default Value |
|-----------------|-----------------------------------------------------------------------------------------------------------------|--------|---------------|
| radius          | Radius that contains the torus knot.                                                                            | number | 1             |
| radiusTubular   | Radius of the tubes of the torus knot.                                                                          | number | 0.2           |
| segmentsRadial  | Number of segments along the circumference of the tube ends. A higher number means the tube will be more round. | int    | 36            |
| segmentsTubular | Number of segments along the circumference of the tube face. A higher number means the tube will be more round. | int    | 32            |
| p               | How many times the geometry winds around its axis of rotational symmetry.                                       | int    | 2             |
| q               | How many times the geometry winds around a circle in the interior of the torus.                                 | int    | 3             |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: torusKnot; radius: 0.5; radiusTubular: 0.1; p: 2; q: 5" material="color: magenta"></a-entity>
</a-scene>
```

### `triangle`

The `triangle` geometry creates a flat two-dimensional triangle. Because triangles are flat, A-Frame will render only a single face, which is the one with `vertexA`, `vertexB`, and `vertexC` appear in counterclockwise order on the screen, unless we specify `side: double` on the `material` component.

```html
<a-entity geometry="primitive: triangle" material="side: double"></a-entity>
```

| Property | Description                                | Type   | Default Value |
|----------|--------------------------------------------|--------|---------------|
| vertexA  | Coordinates of one of the three vertices   | vec3   | 0 0.5 0       |
| vertexB  | Coordinates of one of the three vertices   | vec3   | -0.5 -0.5 0   |
| vertexC  | Coordinates of one of the three vertices   | vec3   | 0.5 -0.5 0    |

**Example:**

```html
<a-scene>
  <a-entity geometry="primitive: triangle; vertexA: -1 0 0; vertexB: 1 0 0; vertexC: 0 1 0" material="color: brown; side: double"></a-entity>
</a-scene>
```