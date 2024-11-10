# canim (C#)

- OpenGL
- OpenCL

## Scene

Everything is part of a scene, the scene acts as the owner and container for all objects and resources.

- 3D Coordinate System
- Camera space
- XY plane (default)
- Camera

### Mesh Builders

- DataSet to Mesh
- Text to Mesh
- 2D Curve to Mesh
- 3D Curve to Mesh
- 2D Shape to Mesh
- 3D Shape to Mesh
- 2D Function to Mesh
- 3D Function to Mesh

### Fundamentals

- Time is the fundamental unit
- Scene -> Sequence -> Frame
- Camera
- Mesh
- Sampler
- Modifier

- Precalculated data is wrapped by a Sampler which can be used to sample the data, together with a Mesh Builder to produce a Mesh each frame
- Functions that produce data are wrapped by a specific Sampler which can be used to sample the function, together with a Mesh Builder to produce a Mesh each frame

### Objects

Fundamental Object is a Mesh, a Mesh is a collection of primitives, vertices and indices and can be rendered as points, lines, or filled shapes

- Text is a Mesh
- Curve is a Mesh
- 2D Shapes (Rectangle, Circle, Star, Triangle, Hexagon, Octagon, etc., all Meshes)
- 3D Shapes (Cube, Sphere, Cylinder, Cone, Pyramid, Beam, etc., all Meshes)

### Morphing and Animation

Morphing between two Meshes results in a new Mesh, we transform the vertices of the other Mesh into the object space of the first Mesh and then interpolate between the vertices.
For Morphing to work best, we might need to tell one of the Meshes to use the same vertex order and count as the other Mesh.

Note: We might need to use GPU Compute for this to increase performance.

### Vector/Matrix Transformations

- Translation
- Rotation
- Scale
- Shear

### (Time) Temporal Transformations

- Tracking velocity changes and reacting to them
- Tracking acceleration changes and reacting to them
- Tracking size changes and reacting to them
- Tracking mass/density/volume or any other property changes and reacting to them

### Attribute Modifiers

- Position, Rotation, Scale
- Color
- Transparency
- Thickness
- Dither a line
- Dither a filled shape

### Rendering Effects

Post processing effects?

- Glow
- Blur

#### MP4 Generation

- https://github.com/jimm98y/SharpMp4Parser
