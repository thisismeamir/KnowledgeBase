---
sticker: lucide//newspaper
---
# Curvature

> Gravitation is manifest in relative acceleration of neighboring test particles


Where's geometry in a world of Local Lorentzian spaces? Gravitation seems to have disappeared. Everywhere the geometry of spacetime is locally Lorentzian. Note the apple again, the re-convergence of two nearby geodesics that were divergence from a common point. Consider two test particles in a spaceship around the earth. What gravitational physics is to be seen here? 

Nothing (because we already said that this is an inertial reference frame), Relative to the spaceship and therefore relative to each other, the two test particles move in a straight line with uniform velocity. Increase the precision of measurement until one begins to discern the gradual acceleration the test particles away from each other. The source of these accelerations is in Newtonian language, the tide-producing action of the Earth.   

To the observer in the spaceship, however, no Earth is to be seen. And following Einstein, he knows it is important to analyze motion locally. 

He represents the separation of the new test particle from the fiducial test particle by a vector $\xi^k$. For the acceleration of this separation, one knows from Newtonian physics what he will find (In Cartesian and $z$-axis is in the radial direction):

$$
\begin{align}
\frac{d^2\xi^x}{dt^2} &= -\frac{Gm_{\text{conv}}}{c^2 r^3}\xi^x\\
\frac{d^2\xi^y}{dt^2} &= -\frac{Gm_{\text{conv}}}{c^2 r^3}\xi^y\\
\frac{d^2\xi^z}{dt^2} &= \frac{Gm_{\text{conv}}}{c^2 r^3}\xi^z
\end{align}
$$
---

***Proof:***
In Newtonian physics the acceleration of a single particle toward the center of the Earth in conventional units of time is $Gm_{\text{conv}}/r^2$,  where $G$ is the Newtonian constant of gravitation and $m_{\text{conv}}$ is the mass of the Earth in conventional units of grams.

In  geometric units of time the acceleration is $Gm_{\text{conv}}/c^2r^2$. When the two particles are separated by a distance $\xi$ perpendicular to $r$, the one downward acceleration vector is out of line with the other by the angle $\xi/r$. 

Consequently one particle accelerates toward the other by the stated amount. 

When the separation is parallel to $r$, the relative acceleration is given by evaluating the Newtonian acceleration at $r$ and $r+\xi$ , and taking the difference. 

In conclusion, the "*local tide-producing acceleration*" of Newtonian gravitation theory provides the local description of gravitation that Einstein bids one to seek.

---

In a space of more than two dimensions, an equation of the same general form applies, with several differences. In two dimensions the direction of acceleration of one geodesic relative to a nearby, fiducial geodesic is fixed uniquely by the demand that their separation vector, be perpendicular to the fiducial geodesic. Not so in three dimensions or higher. There $\xi$ can remain perpendicular to the fiducial geodesic by rotate about it. Thus, to specify the relative acceleration uniquely, one must give not only its magnitude, but also its direction. 

The relative acceleration in three dimensions and higher, then, is a vector. We would call it
$$
\frac{D^2\xi^\alpha}{ds^2}.
$$
Why not simple derivative? Because our coordinate system is completely arbitrary. The twisting and turning of the coordinate lines can induce changes from point to point in the components. Consequently, the accelerations of the components $d^2 \xi^\alpha/ds^2$ are generally not equal to the components of the more general acceleration we just defined (the one with $D$).

---
**Curvature of What?**
Nothing seems more attractive at first glance than the idea that gravitation is a manifestation of the curvature of space, and nothing more ridiculous at a second glance. How can the tracks of a ball and of a bullet be curved so differently if that curvature arise from the geometry of space? 

![[Pasted image 20241130181027.png]]


No wonder that great Riemann did not give the world a geometric theory of gravity. He worked to find a unified account of electricity and gravitation but because he thought of *space and curvature of space* instead of *spacetime and the curvature of spacetime* he somewhat didn't succeed.

To make that forward step took special relativity. Depicted in spacetime, the tracks of ball and bullet appear to have comparable curvature. In fact, however, neither track has any curvature at all. They both look curved picture below,

![[Pasted image 20241218194242.png]]

Only because one has forgotten that the spacetime they reside in is itself curved. Curved precisely enough to make these tracks the straightest lines in existence (*"geodesics"*).

If it is at first satisfying to see curvature, and curvature of spacetime at that, coming to the fore in so direct a way,  then a little more reflection produces renewed sense of concern. Curvature with respect to what? 

Not with respect to the laboratory. The earth-bound laboratory has no simple status whatsoever in a proper discussion.
1. It is no Lorentz frame. 
2. Even to mention the earth makes one think of an action-at-a-distance version of gravity.
In contrast, it was the whole point of Einstein that physics looks simple only when analyzed locally. To look at local physics, however, means to compare one geodesic of one test particle with geodesics of other test particles traveling nearby with nearly the same directions and nearly the same speeds. 

Then one can "*look at the separations between these nearby test particles and form the second time-rate of change of these separations and the equation of geodesic derivation* read out the curvature of spacetime."

---
## Riemann Curvature Tensor

> Riemann tensor, through equation of geodesic deviation, produces relative accelerations

How can we determine the components of the relative acceleration from the given derivative? By a geometrical object called the *Riemann curvature tensor, "Riemann"* is the higher-dimensional analog of the Gaussian curvature  $R$ of our apple's surface.

> Riemann is the mathematical embodiment of the bends and warps in spacetime.

> And Riemann is the agent by which those bends and warps produce the relative acceleration of Geodesics.

Riemann tensor, like the metric can be thought of as a family of machines, one machine residing at each event in spacetime. Each machine has three slots for the insertion of three vectors:
$$
\text{Riemann}(\text{slot1},\text{slot2},\text{slot3})
$$
Choose a fiducial geodesic (free-particle world line) passing through an event $Q$, and denote its unit tangent vector there by:

$$
u^\alpha = dx^\alpha/d\tau
$$
Choose another, neighboring geodesic, and denote by $\xi^\alpha$ its perpendicular separation from the fiducial geodesic. Then insert $u^\alpha$ into the first slot of *Riemann* at $Q$, $\xi^\alpha$ into the second slot and $u^\alpha$ into the third. 

Riemann will give out a new vector, which is the negative of the relative acceleration of the two geodesics.
$$
D^2\xi^\alpha /d\tau^2 + \text{Riemann}(u^\alpha, \xi^\beta, u^\gamma) = 0
$$
==The Riemann tensor, like the metric tensor, and like all other tensors is a linear machine. The vector it puts out is a linear function of each vector inserted into a slot.== Consequently, in any coordinate system the components of the vector put out can be written as a *trilinear function* of the components of the vectors put in.

$$
r^\sigma = \text{Riemann}(u^\alpha, v^\beta, w^\gamma) = R^\sigma_{\alpha\beta\gamma}u^\alpha v^\beta w^\gamma
$$
In terms of components, the equations of geodesic deviation states:

$$
\frac{D^2\xi^\alpha}{d\tau^2} + R^{\alpha}_{\beta\gamma\delta}\frac{dx^\beta}{d\tau}\xi^\gamma\frac{dx^\delta}{d\tau} =0 
$$

> Equation of geodesic deviation is analog of Lorentz force law!

In Einstein's geometric theory of gravity, this equation of geodesic deviation summarized the entire effect of geometry on matter. It does for gravitation physics what the Lorentz force equation does for electromagnetism.

$$
\frac{D^2 x^\alpha}{d\tau^2} - \frac em F^\alpha_{\cdot \beta}\frac{dx^\alpha}{d\tau}
 =0 $$
---
**Equation of Motion under the Influence of a gravitational field and an electromagnetic field, compared and contrasted**

| Question                                                                               | Electromagnetism                                                                                                               | Gravitation                                                                                                                                                    |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Acceleration is defined for one particle?                                              | Yes                                                                                                                            | No                                                                                                                                                             |
| Acceleration definition                                                                | Actual world line compared to world line of uncharged "fiducial" test particle passing through same point with same 4-velocity | Already an uncharged test particle, which can't accelerate relative to itself! Acceleration measured relative to a nearby test particle as fiduciary standard. |
| Acceleration depends on all four components of the 4-velocity of the particle?         | Yes                                                                                                                            | Yes                                                                                                                                                            |
| Universal acceleration for all test particles in same locations with same  4-velocity? | No; is proportional to $e/m$                                                                                                   | Yes                                                                                                                                                            |
| Driving field                                                                          | Electromagnetic field                                                                                                          | Riemann curvature tensor                                                                                                                                       |
| Ostensible number of distinct components of the driving field                          | $4\times 4=16$                                                                                                                 | $4^4 = 256$                                                                                                                                                    |
| Actual number when allowance is made for symmetries of tensor                          | 6                                                                                                                              | 20                                                                                                                                                             |
| Names for more familiar of these components                                            | 3 electric, 3 magnetic                                                                                                         | 6 components of local Newtonian tide-producing acceleration                                                                                                    |

> Components of Riemann tensor evaluated from relative accelerations of slowly moving particles

Using geometrized units, and using the Newtonian theory of gravity, one can readily evaluate nine of the most interesting components of the Riemann curvature tensor near the Earth or the sun. The method is the gravitational analog of determining the electric field strength by measuring the acceleration of a slowly moving charged particle. 

> This ends the survey of the effect of geometry on matter, *effect of curvature of apple in causing geodesics to cross,* Now for the effect of matter on geometry


###### Moving Backward $\rightarrow$ [[4 Time]]
