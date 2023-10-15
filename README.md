Followed: 
[Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)

use `main > image.ppm` to redirect to an image file.

## Notes

### rendered image setup

`viewport_width`: don't use `aspect_ratio` because it is the ideal ratio and may not be the actual ratio between `image_width` and `image_height`

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
C &= (A-C) \cdot (A-C) - r^2
\end{aligned}
$$
