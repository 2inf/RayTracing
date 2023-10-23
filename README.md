Followed: 
[Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)

use `main > image.ppm` to redirect to an image file.

# Notes

## 3. The vec3 Class

## 4. Rays, a Simple Camera, and Background

### Sending Rays Into the Scene

* rendered image setup

`viewport_width`: don't use `aspect_ratio` because it is the ideal ratio and may not be the actual ratio between `image_width` and `image_height`

## 5. Adding a Sphere

### ray-sphere intersection

the vector from center $C=(C_x,C_y,C_z)$ to point $P=(x, y, z)$ is $(P-C)$, then the sphere in vector form:

$$
(P-C)(P-C)=r^2
$$

we want to know if our ray $P(t)=A+tb$ ever hits the sphere anywhere, looking for any $t$ where this is true:

$$
((A+tb)-C)((A+tb)-C)=r^2
$$

$$
t^2b\cdot b + 2tb\cdot (A-C) + (A-C) \cdot (A-C) = r^2
$$

ray-sphere intersection for the a/b/c values are:

$$
\begin{aligned}
a &= b\cdot b \\
b &= 2b \cdot (A - C) \\
c &= (A-C) \cdot (A-C) - r^2
\end{aligned}
$$

consider $b=2h$ then

$$
\frac{-b\pm\sqrt{b^2-4ac}}{2a}=\frac{-h\pm\sqrt{h^2-ac}}{a}
$$

## 6. Surface Normals and Multiple Objects

### Common Constants and Utility Functions

throw common useful constants and future utility functions in `rtweekend.h`

### An Interval Class

implement an interval class to manage real-valued intervals with a minimum and a maximum.

## 7. Moving Camera Code Into Its Own Class

consolidate our camera and scene-render code into `camera` class, responsible for two jobs:

1. Construct and dispatch rays into the world
2. Use the results of these rays to construct the rendered image.