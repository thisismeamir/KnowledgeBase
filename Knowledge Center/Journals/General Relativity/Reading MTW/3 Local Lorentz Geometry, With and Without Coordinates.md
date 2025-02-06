---
sticker: lucide//newspaper
---
# Local Lorentz Geometry, With and Without Coordinates

> Local Lorentz geometry is the spacetime analog of local Euclidean geometry.

## Local Euclidean Geometry
What does it mean to say that the geometry of a tiny thumbprint on the apple is Euclidean?
- *Coordinate-free Language (Euclid):* Given a line $AC$. Extend it by an equal distance $CZ$. Let $B$ be a point not on $AZ$ but equidistant from $A$ and $Z$. Then:
	$$
	S_{AB}^2 = S_{AC}^2 + S_{BC}^2
	$$
	![[Pasted image 20241129223545.png]]
- *Language of Coordinates (Descartes):* From any point $A$ to any other point $B$ there's a distance $s$ given in suitable coordinates by:
	$$
	S_{AB}^2 =[x^1(B) - x^1(A)]^2 + [x^2(B)-x^2(A)]^2
	$$
	if one succeeds in finding any coordinate system where this is true for all points $A$ and $B$ in the thumbprint, then one is guaranteed that 
	1. This coordinate system is locally Euclidean
	2. The geometry of the apple's surface is locally Euclidean.
	![[Pasted image 20241129223600.png]]
## Local Lorentz Geometry
What does it mean to say that the geometry of a sufficiently limited region of spacetime in the real physical world is Lorentzian?
- *Coordinate-free Language (Robb 1936)*:
  Let $AZ$ be the world line of a free particle. 
  Let $B$ be an event not on this world-line. 
  Let a light ray from $B$ strike $AZ$ at the event $Q$.
  Let a light ray take off from such an earlier event $P$ along $AZ$ that it reaches $B$. Then the proper distance $S_{AB}$ (spacelike separation) or propertime $\tau_{AB}$ (timelike separation) is given by:
  $$
  S_{AB}^2 \equiv -\tau^2_{AB} = -\tau_{AQ}\tau_{AP}
  $$
  ![[Pasted image 20241129223608.png]]
	Proof of above criterion for local Lorentz geometry, using coordinate methods in the local Lorentz frame where particles remains at rest:
	$$
	\tau^2_{AB} = t^2 - x^2 = (t-x)(t+x) = \tau_{AP}\tau_{AQ} 
	$$
	![[Pasted image 20241129224029.png]]
- *Language of Coordinates (Lorentz, Poincare, Minkowski, Einstein)*: From any event $A$ to any other nearby event $B$, there is a proper distance or proper time, given in suitable coordinates by:
$$
S_{AB}^2 = -\tau_{AB}^2 = -[x^0(B) - x^0(A)]^2 + \sum_{i=1}^3[x^i(B)-x(A)^i]
$$
![[Pasted image 20241129224040.png]]

## Statement of Fact
The geometry of an apple's surface is locally Euclidean everywhere. The geometry of spacetime is locally Lorentzian everywhere.

## Local Geometry in the Language of Modern Mathematics
### Metric for any Manifold
At each point on the apple, at each event of spacetime, indeed, at each point of any "Riemannian Manifold", there exists a geometrical object called the *metric tensor* $g$.

It is a machine with two input slots for the insertion of two vectors:
$$
g( \text{slot 1}, \text{slot 2} )
$$
If one inserts the same vector into both slots, one gets out the square of the length of that vector:
$$
g(\vec u, \vec u) = u^2
$$
If one inserts two different vectors, $u$ and $v$, one gets out a number called the *"scalar product of $u$ on $v$"* 
$$
g(u,v)= g(v,u) = u\cdot v = v\cdot u
$$
The metric is a linear machine, which means
$$
\begin{align}
g(2u + 3w, v) &= 2g(u,v) + 3g(w,v)\\
g(u,av + bw) &= ag(u,v) + bg(u,w)
\end{align}
$$
Consequently, in a given (arbitrary) coordinate system, its operation on two vectors can be written in terms of their components as a bi-linear expression:
$$
g(u,v) = g_{\alpha\beta}u^\alpha v^\beta
$$
The quantities $g_{\alpha\beta}$ are the components of the metric in a given coordinate system.
Since we already investigated what should the product look like in local Euclidean and local Lorentzian, we can see that on the apple the metric is:

$$
g_{\alpha\beta} = \delta_{\beta}^\alpha
$$
and with flat spacetime:
$$
g_{00} = -1, \ g_{ij} = \delta_{ij}
$$
This flat metric if often denoted as $\eta_{\alpha\beta}$.

###### Moving Forward $\rightarrow$ [[4 Time]]
###### Moving Backward $\rightarrow$ [[2 Weightlessness]]
