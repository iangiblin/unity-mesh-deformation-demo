# unity-mesh-deformation-demo
A single Unity C# script which can be attached to a sphere and will deform it at runtime.

This is meant as an absolutely boiled-down example of a working script to do this job. I hope it is pretty easy to follow. You can extend or modify it to do whatever transformations you want.

![constriction](https://user-images.githubusercontent.com/39740472/149645905-7d1e9fc1-99b0-42d2-9bb0-4ffdcd829b1c.gif)

The main gotcha with mesh deformation (I think) is that <I>each corner of a shape may actually be multiple vertices</I> - this is because each triangle ("Tri") is distinct and a separate component. So a cube for example has 8 corners but many more vertices - I think it is 6 (sides) * 2 (triangles per side) * 3 (verts per triangle) = 36 vertices even though only 8 corners when we picutre it in 3D.

The overlapping vertices do not matter in this example because the transformation we apply is just a mathematical operation on each vertex's point. So if two vertices happen to co-exist then they get exactly the same start and end points. But if you want to randomly purturb the vertices then you need to figure out which ones are overlapping and make sure you move them together, otherwise your surface will facture.

