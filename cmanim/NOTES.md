# canim

- OpenGL
- OpenCL

## Scene

Everything is part of a scene, the scene acts as the owner and container for all objects and resources.

- 3D Coordinate System
- Camera space
- XY plane (default)
- Camera

### Mesh Builders

A mesh builder pulls data from an interface that is providing the following sets of data:

- Vertices
- Normals
- Colors (RGBA)
- Primitives (Triangles, Lines, Points)
- Custom data (UV, Tangents, Bitangents, etc.)

Any Producer providing the above data streams can be used to build a visual representation, for example:

- Text
- Curves
- Shapes
- Lines
- Points

### Fundamentals

- Scene -> Sequence -> Frame (Time)
- Camera
- Mesh
- Sampler
- Modifier

- Precalculated data is wrapped by a Provider which can be used to sample the data, together with a Mesh Builder to produce a Mesh each frame
- Functions that produce data are wrapped by a Provider which can be used to sample the function, together with a Mesh Builder to produce a visual representation each frame

### Visual Object

Fundamental Visual Object is a Vertex + Index Buffer + Primitive Type + VS/PS Shader (a Mesh).

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

A Modifier is a function that takes an attribute and modifies it in some way over a period of time. Since there are many ways to modify an attribute over time (e.g. linear, exponential, logarithmic, ease-in, ease-out, etc.), we can define a Modifier as a function that takes a time value and returns a value that can be used to modify the attribute.

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
