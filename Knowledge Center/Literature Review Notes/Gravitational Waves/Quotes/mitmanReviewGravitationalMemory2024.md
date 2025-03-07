Comment: 22 pages, 8 figures. Matches published version in CGQ's focus issue: Gravitational-Wave Memory Effects: From Theory to Observation

# Review Notes on: A Review of Gravitational Memory and BMS Frame Fixing in Numerical Relativity

A challenge in modern physics is to be able to perform tests for the theory of general relativity. Since this theory is observable in greater scales than limited laboratories on Earth. Considering this one of the best tests that is currently at our hands is considering gravitational waves.

Gravitational waves are created at extreme event on spacetime, large masses (such as black holes or neutron stars) that can bend the fabric of spacetime largely can make propagation of energy within it. Theoretical approach to gravitational waves had been understood from early on but observation of them happened in the last decade (2015) for the first time.

Even though the start of the theoretical approach look easy, it would be exceptionally complicated to solve these systems (binary black holes, binary neutron stars, etc.) analytically. We’ve got perturbation but at the end of the day, we are bounded to use numerical analysis and computer simulations to get a good perspective on the matter.

## Numerical Relativity

Numerical relativity is our theoretical and computational approach of the physics of the spacetime. Although in theory it can achieve arbitrary

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=1&annotation=JGNEMP37) “NR can still fail to accurately simulate GR if the code infrastructure is not formulated correctly or if the necessary numerical resolution is not achieved.” ([Mitman et al., 2024, p. 1](zotero://select/library/items/SNRQ7CW2)) NR can still fail.  

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=1&annotation=9SYTG7K6) “One such example of this inaccuracy was the inability of NR simulations to resolve a collection of observables in GR colloquially referred to as memory effects [12–14]. These effects are not-yet observed, nonlinear predictions of GR that physically correspond to the net displacement that two freely-falling observers will experience due to the passage of transient GWs.” ([Mitman et al., 2024, p. 1](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=1&annotation=DPZ7F4WT) “However, apart from being a curious prediction of GR, what makes memory effects particularly tantalizing is that they are intimately tiedthrough conservation laws—to the symmetry group of future null infinity—part of the asymptotic boundary of spacetime.” ([Mitman et al., 2024, p. 1](zotero://select/library/items/SNRQ7CW2))

## Pedagogical Approach to BMS Memory

### Motivation

Choosing coordinates is an important yet confusing part of researching on Einstein’s theory. This had even lead to issues regarding if Gravitational Waves are real, or are they only artifacts of the gauge. Luckily this confusion was resolved when Pirani proved the existence of gravitational waves using Tetrad Methods and Worldline particles.

Despite that Pirani’s formulation was of no use for predicting particular systems (such as black hole mergers), but only for theoretical perspectives,

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=2&annotation=undefined) “For this, a more suitable framework was developed in a series of works by Bondi, van der Burg, Metzner, and Sachs [15, 16, 26–28].” ([Mitman et al., 2024, p. 2](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=2&annotation=undefined) “Their approach to studying GWs, which we describe in Sec. II B, involves constructing an explicit coordinate system and assuming a particular, but well-motivated asymptotic behavior of the spacetime metric in those coordinates.” ([Mitman et al., 2024, p. 2](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=2&annotation=76IDLJ7X) “As an alternative perspective regarding the subtleties of coordinates in GR, consider a numerical simulation. At the simplest level, numerical relativists must produce waveforms as tables of timestamps and corresponding GW strain values measured at various angular locations encompassing the source.” ([Mitman et al., 2024, p. 2](zotero://select/library/items/SNRQ7CW2))

However, the meaning of those time coordinates, the angular locations at which the strain is measured, and the basis with respect to which the strain is evaluated rely on the essentially arbitrary coordinates used in numerical simulation.

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=PK52BKZQ) “Despite confusing declarations that may be found in the NR literature, no GW extraction method can produce “invariant” results in the sense of being independent of the choice of coordinates [29]. Even at linear order in the size of the gauge perturbation, every waveform description is coordinate-dependent. But this issue is not unique to NR simulations. Other gravitational wave modelers, such as those working in post-Newtonian (PN) or even post-Minkowskian (PM) theory, face similar ambiguities. Ideally, we would resolve these coordinate issues in a consistent way, so that waveforms from other simulations, or other models, can be compared to each other.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

Although there’s a rich set of coordinate systems to be used for the study of gravitational waves, working with all this possibilities is not feasible. Instead we need to limit ourselves with some, that we are so motivated to use.

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=RKCDP7FD) “one property that we might impose is that the coordinate systems we consider be adapted to trajectories of inertial observers.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=85SWTGQ6) “That is, curves that have constant spatial coordinates could be timelike geodesics, and the time coordinate for those curves could be the proper time measured on those geodesics.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=MBSQH8TQ) “While this would certainly be possible, one issue that arises is that the coordinates we consider would then depend on their initial conditions, and would surely encounter coordinate singularities.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=PP3Y5FF2) “But, it turns out that if we instead consider the region of spacetime infinitely far away from the source, then it is sometimes possible4 to find a set of coordinates that is asymptotically inertial.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

The Sometimes is for the following reason:

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=GQMUBXN9) “This possibility rests on some fairly stringent requirements about the spacetime, including the existence of the infinite radius limit, and the fall-off behavior of the metric in that limit. In particular, these requirements rule out direct application to, for example, FLRW spacetimes. Nonetheless, recent work has sought to extend similar analyses to FLRW spacetimes [30–35].” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))

This was in essence what Bondi, Metzner, and Sachs came up with.

[Go to annotation](zotero://open-pdf/library/items/ST2N8AJJ?page=3&annotation=6N3HBU5I) “The core idea is that one should instead model a GW source as an isolated system, with the spacetime approaching Minkowski space far from the source, so that one can then match the coordinates to the more familiar inertial trajectories of Minkowski space.” ([Mitman et al., 2024, p. 3](zotero://select/library/items/SNRQ7CW2))