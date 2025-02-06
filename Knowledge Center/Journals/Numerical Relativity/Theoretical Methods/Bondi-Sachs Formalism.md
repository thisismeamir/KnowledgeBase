---
sticker: lucide//newspaper
---
For a delved into post where I talked about what is of my interest in this formalism (the ones that I have to use in my research) please consider this side-note [[Related Topics of Bondi-Sachs Formalism to 2025 research]]
# Abstract
The [[Bondi-Sachs Formalism]] of [[Knowledge Center/Journals/General Relativity/General Relativity|General Relativity]] is a metric-based treatment of the Einstein equations in which the coordinates are adapted to the null geodesics of the spacetime. It provided the first convincing evidence that mass loss due to gravitational radiation is a non-linear effect of general relativity and that the emission of gravitational waves from an isolated system is accompanied by a mass loss from the system. 

The asymptotic behavior of the Bondi-Sachs metric revealed the existence of the symmetry group at null infinity, the Bondi-Metzner-Sachs group, which turned out to be larger than the Poincare group.

# Introduction 
The Bondi-Sachs coordinates $x^a = (u,r,x^A)$ are based on a family of outgoing null hypersurfaces $u=\text{const}$ The hypersurfaces $x^0 = u= \text{const}$ are null. 

> [!IMPORTANT] 
> The normal co-vector $k_a = -\partial_a u$ satisfies $g^{ab}(\partial_a u)(\partial_b u) = 0$.

so that $g^{uu} = 0$, and the corresponding future pointing vector $k^a = -g^{ab}\partial_b u$ is tangent to the null rays. 

Two angular coordinates $x^A (A = 2,3)$, are constant along the null rays are constant along the null rays, $k^a\partial_a x^A = 0$, so that $g^{uA} = 0$. 

The coordinate $x^1 = r$, which varies along the null rays, is chosen to be an areal coordinate such that $\det[g_{AB}] = r^4\mathcal{q}$, where $q$ is the determinant of the unit sphere metric $q_{AB}$ associated with the angular coordinates $x^A$.

> [!IMPORTANT] For Standard Spherical Coordinates
> $$q_{AB} = \text{diag}(1,\sin^2\theta)$$

The contravariant and covariant components ($g^{ab}, g_{ab}$) are related by:
$$
g^{ac}g_{cb} = \delta^a_b
$$
which in particular implies that
$$
\begin{align}g_{rr} &=0 \\ g_{rA} &=0\end{align} 
$$
Given these the metric takes the Bondi-Sachs form:

> [!DANGEROUS] Bondi-Sachs Metric
> $$\begin{align}g_{ab}dx^adx^b  = &-\frac{V}{r}e^{2\beta} du^2 - 2e^{2\beta} dudr \\ &+ r^2 h_{AB} \left(dx^A -U^A du\right)\left(dx^B-U^B du\right)\end{align}$$

