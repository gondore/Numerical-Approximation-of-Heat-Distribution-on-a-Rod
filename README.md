# Numerical-Approximation-of-Heat-Distribution-on-a-Rod
Supporting information for a numerical approximation project by Justin Loi, Aamina Mohammed, Jason Dai, Wing Pok Lee, and Cecilia Han

We generate data for the heat error function using natural cubic splines and use it to graph the heat distribution of a rod. 

The error function $\text{erf} : \mathbb{R} \rightarrow \mathbb{R}$ is defined as

$$
\text{erf}(x) := \frac{2}{\sqrt{\pi}} \int_{0}^{x} e^{-t^2} \, dt
$$

(The factor $\frac{2}{\sqrt{\pi}}$ is a normalizing constant.) Its name comes from its frequent use in probability and statistics, but it also appears in other branches of mathematics, such as partial differential equations (in particular in solving the heat equation, as we shall see).

For simplicity, we have taken the diffusion constant \(k\) to be 1. The particular solution of the PDE involved is given by 


$$ u(x, t) = \frac{1}{\sqrt{4\pi t}} \int_{0}^{\infty} e^{-\frac{(y - x)^2}{4t}} \, dy = \frac{1}{\sqrt{\pi}} \int_{-\frac{x}{\sqrt{4t}}}^{\infty} e^{-z^2} \, dz $$
