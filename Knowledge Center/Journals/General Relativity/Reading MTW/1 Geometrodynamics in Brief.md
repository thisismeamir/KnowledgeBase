---
sticker: lucide//newspaper
---
# Geometrodynamics in Brief
## The Parable of the Apple
From the route of two ants on an apple, one understands quite illustrative, the geometric theory of gravity.

> **Einstein's local view of gravity contrasts with Newton's action at a distance.**

> **Physics is simple when viewed locally.**

1. Locally geodesics appear straight
2. Over more extended regions of space and time, geodesics receding from each other gather at a rate governed by the curvature of spacetime, and this effect that geometry enforces on matter is what old-fashioned physics calls *Gravitation*
3. Matter in return gives spacetime it's curvature.

> Space acts on matter, telling it how to move. Matter reacts back on back on space, telling it how to curve. Thus the matter here influences the matter there. That's Einstein's explanation for Gravitation.

## Spacetime With and Without Coordinates

> But with all the daring in the world... How is one to drive a nail into spacetime to mark a point?

Nature provides a good help here, as Einstein was first to emphasize the point. Characterize the point by what's happening there!
Give the point of spacetime the name "*event*".

To say that the event marks a collision of such and such a photon with such and such a particle is identification enough. The world lines of that photon and that particle are rooted in the past and stretch into the future. They have connections with other world lines. These nearby world lines are in turn linked in many ways with other world lines (some so remote).

One does not need to have coordinates, just following all the events and world lines would suffice to have a description of what's happening in the universe. Despite that, having coordinates is very logical and convenient (we are used to it!). Otherwise searching for an specific event in the history of cosmos would be redundant.

![[Pasted image 20241123192455.png]]

Introduce Coordinates, these are four indexed numbers per event:

$$
(x^0, x^1, x^2, x^3)
$$
Coordinates do not generally measure length. 

| Concept                       | Description                                                                                                                                                                                                                   | Notation                                                                                                                                |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Events                        | Events are denoted by capital script, one-letter Latin names. Sometimes subscripts are used.                                                                                                                                  | 𝒫, ℒ, 𝒬, ℛ, 𝒫₀, 𝒫₁, etc.                                                                                                            |
| Coordinates of an event 𝒫    |                                                                                                                                                                                                                               | t(𝒫), x(𝒫), y(𝒫), z(𝒫),<br>x⁰(𝒫), x¹(𝒫), x²(𝒫),<br>x³(𝒫),<br>or more abstractly<br>xᵃ(𝒫) or xᵅ(𝒫)<br>(Greek indices: 0,1,2,3) |
| Time coordinate               | When one of the four is picked to play this role                                                                                                                                                                              | x⁰(𝒫)                                                                                                                                  |
| Space coordinates             | Latin indices take values 1, 2, or 3                                                                                                                                                                                          | x¹(𝒫), x²(𝒫), x³(𝒫)<br>x(𝒫), y(𝒫), z(𝒫)                                                                                           |
| Shorthand notation            | One soon tires of writing explicitly the functional dependence of the coordinates. For coordinates of event 𝒫 and space coordinates. Note: x^i depends not only on choice of 𝒫 but also on arbitrary choice of coordinates! | xᵃ<br>xⁱ                                                                                                                                |
| Other coordinates             | For the same event 𝒫 may be denoted                                                                                                                                                                                          | x̄ᵃ(𝒫) or just x̄ᵃ,<br>x̃ᵃ(𝒫) or just x̃ᵃ,<br>x'ᵃ(𝒫) or just x'ᵃ                                                                     |
| Transformation                | From one coordinate system to another is achieved by the four functions                                                                                                                                                       | x̄⁰(x⁰, x¹, x², x³),<br>x̄¹(x⁰, x¹, x², x³),<br>x̄²(x⁰, x¹, x², x³),<br>x̄³(x⁰, x¹, x², x³),<br>or more succinctly<br>x̄ᵃ(x)            |
| Separation vector*            | Little arrow reaching from one event ℒ to neighboring event 𝒫. Can be characterized by coordinate-value differences                                                                                                          | u or v or ξ, or 𝒫 - ℒ<br>ξᵃ ≡ xᵃ(𝒫) - xᵃ(ℒ),<br>ξⁱ ≡ xⁱ(𝒫) - xⁱ(ℒ)                                                                   |
| Transformation of components  | Of a vector from one coordinate system to another is achieved by partial differential equations                                                                                                                               | ξ̄ᵃ = ∂x̄ᵃ/∂xᵇ ξᵇ                                                                                                                       |
| Einstein summation convention | Any index that is repeated in a product is automatically summed on                                                                                                                                                            | ∂x̄ᵃ/∂xᵇ ξᵇ = Σᵇ ∂x̄ᵃ/∂xᵇ ξᵇ                                                                                                            |

*Note: This definition of a vector is valid only in flat spacetime. The refined definition ("tangent vector") in curved spacetime is not spelled out here (see Chapter 9), but flat-geometry ideas apply with good approximation even in curved geometry, when the two points are sufficiently close.

**Note: These formulas are precisely accurate only when the region of spacetime under consideration is flat and when in addition the coordinates are Cartesian. Otherwise they are approximate—though they become arbitrarily good when the separation between points and the length of the vector become arbitrarily small.


> Coordinate singularities normally unavoidable.

There are many ways that coordinate systems are imperfect. Singularities, where the coordinates cannot be as good differentiating the points (or there might be multiple coordinates to explain one point). Can this be avoided? A theorem states **no**, Two is the minimum number of *coordinate patches* required to cover the two-sphere without singularities.

*This emphasizes our point, where events are primary, coordinates are just the means of bookkeeping.*

> Continuity of Spacetime

In the figure above we have shown a very small number of the possible worldlines. If we were to  put all there is, from such figure one can in imagination step to the idealized limit: an infinitely dense collection of light rays and of worldlines of infinitesimal test particles. 

> The mathematics of manifolds applied to the physics of spacetime

With this idealized physical limit, the mathematical concept of a continuous four-dimensional *Manifold* has a one-to-one correspondence; and in this limit, continuous, differentiable coordinate systems operate.

### Dimensionality of Spacetime: A good test
1. **Initial Point Selection**
   - Start with point $\mathcal{P}$ in n-dimensional manifold
   - Neighborhood is an n-dimensional ball
   - Ball's boundary is a smooth $(n-1)$-dimensional manifold

2. **First Reduction: $(n-1)$ Dimensions**
   - Select point $\mathcal{R}$ on boundary
   - Neighborhood is $(n-1)$-dimensional ball
   - Boundary is smooth $(n-2)$-dimensional manifold

3. **Continue Reduction**
   - Process continues through decreasing dimensions
   - Each step reduces dimension by 1
   - Each boundary is smooth manifold of next lower dimension

4. **Two-Dimensional Stage**
   - Reach point $\mathcal{Q}$ in two-dimensional manifold
   - Neighborhood is two-dimensional ball ("disc")
   - Boundary is smooth one-dimensional manifold (circle)

5. **One-Dimensional Stage**
   - Select point $\mathcal{S}$ on circle
   - Neighborhood is one-dimensional ball (line segment)
   - Boundary consists of two points

6. **Dimensional Counting**
   - Presence of point boundaries confirms one-dimensionality
   - Count backwards to original dimension
   - Total dimension equals number of points used ($\mathcal{P}$, $\mathcal{R}$, $\mathcal{Q}$, $\mathcal{S}$)

7. **Spacetime Application**
   - For spacetime manifold, this process requires 4 points
   - Confirms spacetime is 4-dimensional

This countdown process provides a constructive proof of manifold dimensionality through successive boundary reductions.

This mathematical reasoning about dimensionality makes good sense at all distances (because of the notion of smoothness and infinitesimally close points), but if one judges by the predictions of *Quantum Field Theory*, everything breaks! It predicts violent fluctuations in the geometry at distances on the order of Planck length. 

No one has found any way to escape this prediction. As nearly as one can estimate, these fluctuations give space at small distances a *"multiply connected"* or *"foamlike"* character. This lack of smoothness may well deprive even the concept of dimensionality itself of any meaning at the Plank scale of distances. 

> Difficulty in defining geometry even at classical distances?

If spacetime at small distances is far from mathematical model of a continuous manifold, is there not also at larger distances a wide gap between the mathematical model and physical reality?

> Conclusion

In conclusion, when one deals with spacetime in the context of classical physics, one accepts
1. The notion of "infinitesimal test particle".
2. The idealization that the totality of identifiable events forms a four-dimensional continuous manifold.
Only at the end of this book will a look be taken at some of the limitations placed by the quantum principle on one's way of speaking about and analyzing spacetime.


---
###### Moving Forward $\rightarrow$ [[2 Weightlessness]]
