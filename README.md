# Numerical-Approximation-of-Heat-Distribution-on-a-Rod
Supporting information for a numerical approximation project by Justin Loi, Aamina Mohammed, Jason Dai, Wing Pok Lee, and Cecilia Han


<div style="text-align: center; margin-top: 2em;">
    <span style="font-family: 'Times New Roman', Times, serif; font-size: 2em; font-weight: bold;">
       Numerical Approximation of Heat Distribution on a Rod
    </span>
    <br>
    <span style="font-family: 'Times New Roman', Times, serif; font-size: 1.5em;">
        Justin Loi
    </span>
</div>

We generate data for the heat error function using natural cubic splines and use it to graph the heat distribution of a rod. 

The error function $\text{erf} : \mathbb{R} \rightarrow \mathbb{R}$ is defined as

$$
\text{erf}(x) := \frac{2}{\sqrt{\pi}} \int_{0}^{x} e^{-t^2} \, dt
$$

(The factor $\frac{2}{\sqrt{\pi}}$ is a normalizing constant.) Its name comes from its frequent use in probability and statistics, but it also appears in other branches of mathematics, such as partial differential equations (in particular in solving the heat equation, as we shall see).

![equation](https://latex.codecogs.com/svg.latex?%0A%5Cbegin%7Balign%2A%7D%0Au_t+%26%3D+u_%7Bxx%7D+%26+%281%29+%5C%5C%0Au%7C_%7Bt%3D0%7D+%26%3D+%5Cleft%5C%7B+%5Cbegin%7Barray%7D%7Bll%7D%0A1+%26+%5Ctext%7Bif+%7D+x+%5Cgeq+0+%5C%5C%0A0+%26+%5Ctext%7Bif+%7D+x+%3C+0%0A%5Cend%7Barray%7D+%5Cright.+%26+%282%29%0A%5Cend%7Balign%2A%7D%0A)

Consider the initial value problem
$$\begin{align}
u_t &= u_{xx} \quad (1)\\
u|_{t=0} &= 
\begin{cases}
1, & x \geq 0\\
0, & x < 0
\end{cases} \quad (2)
\end{align}$$

For simplicity, we have taken the diffusion constant \(k\) to be 1. The particular solution of this PDE is given by 




$$ u(x, t) = \frac{1}{\sqrt{4\pi t}} \int_{0}^{\infty} e^{-\frac{(y - x)^2}{4t}} \, dy = \frac{1}{\sqrt{\pi}} \int_{-\frac{x}{\sqrt{4t}}}^{\infty} e^{-z^2} \, dz $$
