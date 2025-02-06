---
sticker: lucide//newspaper
---
A matter distribution with mass-energy density current vector $J^\mu$ and no stresses  is modeled by a stress-energy tensor in the form:
$$
T_{\mu\nu} = 2J_{(\mu}t_{\nu)} - 2\rho t_\mu t_\nu
$$
where $T_{ij} = 0$ and $T_{0\mu} = J_\mu$.

> [!NOTE] 
> Note that $J^\mu = \rho u^\mu = \rho(W,Wv^i/c)$ and that $T_{ij} =\mathcal{O}(v^2/c^2)$, thus the static case considered above is equivalent to consider the slow velocity limit for the source, and taking $T_{ij}\equiv 0$ is equivalent to neglect velocity terms $\mathcal{O}(1/c^2)$ in the source motion.  

The linearized equations read:
$$
\left\{ 
\begin{matrix}
\square \bar h_{0\mu} = -16\pi T_{0\mu} \\
\square \bar h_{ij} =0
\end{matrix}
\right.
$$
If the spatial component of the metric are assumed time-independent, then they are solution of the boundary value problem with the Poisson equation and boundary values $\bar h_{ij}|_{r\rightarrow \infty}$. This implies they are zero:
$$
\partial_t\bar h_{ij} = 0 \Rightarrow \left\{
\begin{matrix}
\Delta \bar h_{ij} =0\\
\bar h_{ij}|_{r\rightarrow \infty} =0
\end{matrix}
\right. \Rightarrow \bar h_{ij} =0
$$

The linearized equations reduce to only for $\bar h_{0\mu}$, that are formally equivalent to the Maxwell equation in Lorentz gauge for the field.
$$
A_\mu := -\frac14 \bar h_{0\mu} = -\frac14 \bar h_{\mu\nu}t^\nu
$$
Once the solution is found the metric is found to be:
$$
\begin{align}
g_{00} &= -1 +2 A_0\\
g_{0i} &= 4A_i
g_{ij} = 1 +2A_0 \delta_{ij}
\end{align}
$$

> [!REMARK] Time-independent solution
> If one further assumes that $\bar h_{0\mu}$ is time-independent a formal solution can be obtained with the usual Green function method for the Poisson equation.
> $$
> \partial_t \bar h_{0\mu} = 0\Rightarrow \left\{
> \begin{matrix} 
> A_0 = -\phi \\ A_i = \int d^3x'\frac{T_{0i}(x')}{|\vec x - \vec x'|}
> \end{matrix}
> \right.
> $$

The metric is then:
$$
\boxed{
g = -\left(1 +\frac{2\phi}{c^2}\right)d(ct)^2 + 4A_i d(ct)dx^i + \left(1- \frac{2\phi}{c^2}\right)\delta_{ij}dx^i dx^j
}
$$
Using the same formulas as in electrodynamics, one then defined from $A_\mu$ the gravitoelectric and gravitomagnetic ($\vec E, \vec B$) fields. The geodesics on this metric in the small velocity limit reduce to those of a particle subject to the Gravitational Lorentz Force.

Consider the Lagrangian for a particle in the weak metric:
$$
\begin{align}
L &= -mc\sqrt{-g_{\mu\nu}\frac{dx^\mu}{dt}\frac{dx^\nu}{dt}} \\ &= -mc^2\sqrt{-g_{00} - 2g_{0i}\frac{v^i}{c} - g_{ij}\frac{v^i v^j}{c^2}}\\ &=-mc^2\sqrt{1- 2A_0 -8 A_i \frac{v^i}{c}- \frac{v^jv_j}{c^2} + 2A_0\frac{v^jv_j}{c^2}}\\
&\approx -mc^2 + \frac m2 v^2 + m\phi +4mc A_i v^i
\end{align}
$$
The above equation implies an equation of motion with the Gravitational Lorentz Force:

$$
\boxed{\ddot{\vec x} = \vec E + 4\vec v\times \vec B}
$$
The difference with normal, electromagnetic lorentz force is that there's no charge, and there's a factor 4 in front of gravitomagnetic field.