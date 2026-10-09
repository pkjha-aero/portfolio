# Wings and Rotors in Atmospheric Turbulence

!!! abstract "In one minute"
    - **Problem.** Blade-resolved CFD of a wind farm or rotorcraft wake is far too expensive,
      but cheaper blade models got tip loads and wake structure wrong.
    - **What I built.** Geometry-based blade models (the actuator line with an elliptic force
      projection, then the **actuator curve embedding**, ACE) in an OpenFOAM LES solver, plus
      statistical tools to study how blades respond to atmospheric turbulence.
    - **Result.** Modeling guidelines that became a reference for the field: 199 citations for
      the 2014 guidelines paper, 86 for the JFM ACE paper, used by groups in Belgium, Israel,
      Denmark and the US, and by the US Navy for ship-airwake pilot training.

## My role

PhD research at Penn State (advisor Sven Schmitz), in collaboration with NREL's (now NLR's) National Wind
Technology Center (Matthew Churchfield, Patrick Moriarty). I developed the models, implemented
them in C++ inside OpenFOAM, ran the LES campaigns on Titan (~4k CPUs), and did the statistical
analysis. Later at Envision Digital I applied the same models to production wind-resource
assessment.

## The modeling problem

The **actuator line model** (ALM) represents each blade as a line of points carrying lift and
drag from airfoil tables. The forces are smeared into the flow as body forces with a Gaussian
kernel of width \(\varepsilon\):

\[
\eta_\varepsilon(r) = \frac{1}{\varepsilon^3 \pi^{3/2}} \exp\!\left[-\left(\frac{r}{\varepsilon}\right)^2\right]
\]

The choice of \(\varepsilon\) controls everything: too small is unstable on an LES grid, too
large smears the tip vortex and over-predicts tip loads.

<figure markdown>
![Actuator line modeling schematic: a turbine blade represented as a line of points in a CFD grid, with lift, drag, thrust and torque vectors](../assets/figures/cp1/alm-schematic.png){ width="560" }
<figcaption>Actuator line modeling: blade forces from airfoil data are projected onto the CFD
grid. From Jha et al., <a href="https://doi.org/10.3390/en8076468">Energies 8 (2015)</a>,
CC BY 4.0.</figcaption>
</figure>

**Contributions, in order:**

1. **Guidelines for the projection** ([JSEE 2014][doi-jsee-2014]). A projection radius that
   varies along the span following an **elliptic distribution**, with rules for choosing
   \(\varepsilon\) on isotropic LES grids. Tested on the NREL Phase VI rotor and the NREL 5-MW
   turbine against measurements and the blade-element code XTURB-PSU.
2. **Accuracy assessment** ([AIAA 2013][doi-aiaa-2013]). How state-of-the-art ALM variants
   compare on wake prediction.
3. **Actuator curve embedding** ([JFM 2018][doi-jfm-2018]). Represents *arbitrary* lifting
   curves (swept, curved, tip-shaped blades), and removes the force overlap and projection
   beyond the tip that make ALM inconsistent. Demonstrated on an elliptic wing, the NREL Phase VI
   rotor (parked and rotating) and the NREL 5-MW turbine.
4. **Rotorcraft** ([AHS 2013][pdf-ahs-2013]). ALM carried over from wind turbines to the
   wake of a helicopter rotor hub, and checked against water-tunnel data
   ([below](#rotorcraft-the-wake-of-a-helicopter-rotor-hub)).

## Wakes, loads and turbulence

With the models in place I asked how atmospheric turbulence and upstream wakes drive the loads
and power of downstream turbines.

<figure markdown>
![Wind-turbine wake regions (near, intermediate, far wake) above an LES vorticity plot of an NREL 5-MW turbine](../assets/figures/cp1/wake-structure.jpg){ width="640" }
<figcaption>Wake regions behind a turbine and the LES vorticity field that resolves them (NREL
5-MW, 8 m/s). Jha et al., <a href="https://doi.org/10.3390/en8076468">Energies 2015</a>,
CC BY 4.0.</figcaption>
</figure>

- **Turbulence transport in a wind farm** ([Energies 2015][doi-energies-2015]). Two NREL 5-MW
  turbines seven diameters apart in neutral and unstable atmospheric boundary layers, and a
  five-turbine staggered farm. Power spectral densities of turbine power reveal the space and time
  scales of atmospheric turbulence. High-resolution surface extracts show how turbulence
  transport recovers the wake's momentum deficit.
- **Blade-load unsteadiness** ([JSEE 2016][doi-jsee-2016]). ALM parameters cause notable
  uncertainty in predicted power, and it comes from the **outer 15% of the span**. Unsteady
  aerodynamics, by contrast, dominates **inboard**.
- **Fluid–structure interaction** ([AIAA 2014][doi-aiaa-2014-fsi]). Actuator line coupled
  tightly to a finite-element structural solver.
- **Icing** ([AIAA 2012][doi-aiaa-2012]). An engineering tool for turbines in cold climates
  ([below](#icing-turbines-in-cold-climates)).

<figure markdown>
![Iso-vorticity surfaces of two interacting wind turbine wakes over a plane colored by axial velocity](../assets/figures/cp1/turbine-interaction.jpg)
<figcaption>Turbine–turbine interaction in atmospheric turbulence: iso-vorticity with axial
velocity on the ground plane. Jha et al., <a href="https://doi.org/10.3390/en8076468">Energies
2015</a>, CC BY 4.0.</figcaption>
</figure>

<figure markdown>
![Five-turbine wind farm LES showing wake breakdown and turbine T1–T4 interaction](../assets/figures/cp1/wind-farm-5-turbines.jpg)
<figcaption>Five NREL 5-MW turbines in unstable atmospheric flow: larger structures, wake breakdown
and the T1–T4 interaction. This dataset (10 TB of CFD output) was featured by Intelligent Light
in <a href="https://drive.google.com/file/d/1aIxq1njxseOAJoyEFwiIlRnyrGQVjPgG/view">Aerospace
America, June 2015</a>. Jha et al., <a href="https://doi.org/10.3390/en8076468">Energies
2015</a>, CC BY 4.0.</figcaption>
</figure>

### What the wind-farm simulations showed

These runs were part of the DOE-funded "Cyber Wind Facility" project at Penn State
(DE-EE0005481), with post-processing in FieldView by Intelligent Light
([AHS 2014][pdf-ahs-2014], [Energies 2015][doi-energies-2015]).

<div class="result" markdown>

- **Atmospheric stability sets array efficiency.** A moderately convective boundary layer
  recovers the wake faster than a neutral one, so the array produces more power. The same
  turbulence raises fatigue loads, especially on the downstream turbine.
- **Power levels off by the third turbine**, confirming in simulation what operators observe in
  real wind farms.
- **Staggering trades a little power for steadier loads.** A staggered row loses a small amount
  of power to the upstream wake even in perfectly aligned wind, but its power fluctuations (a
  proxy for fatigue loads) drop faster than its mean power.
- **The wake recovers unevenly.** A new *dynamic surface clipping* method separated fluxes of
  mass, momentum, power density and TKE above and below hub height. It showed that the lower
  half of the wake lags the upper half by about one turbine spacing.

</div>

<figure class="narrow" markdown>
![Bar charts of mean turbine power and standard deviation of power for turbines 1 to 5](../assets/figures/cp1/five-turbine-power.png){ width="320" }
<figcaption>Five-turbine farm: mean power (top) and its standard deviation (bottom) per turbine.
Power levels off at turbine 3; the staggered turbines 4–5 fluctuate less. Jha et al.,
<a href="https://drive.google.com/file/d/1tgRcl_QXS3K75nF9Q-X2fnJs3jzrlfyX/view">AHS Forum 70
(2014)</a>, © AHS International.</figcaption>
</figure>

## Rotorcraft: the wake of a helicopter rotor hub

Vortical structures shed by a helicopter's rotating hub interact with the main-rotor wake and
drive vibration on the empennage, tail and horizontal stabilizer, yet the turbulent wake physics
is poorly understood. I carried the actuator line over from wind energy to model the hub
([AHS 2013][pdf-ahs-2013]).

- **Modeling.** The hub is treated as a small "wind farm" of actuator lines: the four hub arms
  become an equivalent four-bladed rotor at 85° yaw, the upper and lower spiders become
  additional rotors, and the solid hub body becomes a ten-bladed rotor of solidity one. The finest
  grid is 1/32 of the hub radius, about 0.5% of the blade radius.
- **Validation.** The case matches an industry-representative model hub tested at advance ratio
  0.2 in the 48-inch Garfield Thomas Water Tunnel at ARL Penn State, with LDV, PIV and SPIV
  measurements. The comparison is made about one blade radius downstream, where the horizontal
  stabilizer sits.
- **Result.** The ALM/LES wake captures the dominant per-rev harmonics measured in the tunnel,
  with some overprediction. The prominent structures from the hub break down into smaller-scale
  turbulence downstream, and the retreating blade stub is correctly in reverse flow.

<figure markdown>
![Model rotor hub geometry with measurement locations, its actuator-line representation, and the turbulent wake as an iso-vorticity surface](../assets/figures/cp1/rotor-hub-wake.jpg)
<figcaption>Top: model rotor hub with LDV measurement locations (left) and its actuator-line
representation (right). Bottom: iso-vorticity surface of the computed hub wake at advance ratio
0.2. Schmitz and Jha, <a href="https://drive.google.com/file/d/1f1xQTCkZVE_MsQaSmgrH_dRxouxDmJ9d/view">AHS
Forum 69 (2013)</a>, © AHS International.</figcaption>
</figure>

<figure markdown>
![Time trace and harmonic content of vertical velocity in the far wake, water tunnel vs ALM/LES](../assets/figures/cp1/rotor-hub-vs-water-tunnel.png)
<figcaption>Vertical velocity in the far wake: time trace (left) and per-rev harmonic content
(right), water-tunnel measurement (PSU-GTWT) vs. ALM/LES. The dominant 2/rev and 4/rev content is
captured. Schmitz and Jha, AHS Forum 69 (2013), © AHS International.</figcaption>
</figure>

## Icing: turbines in cold climates

Ice on the blades costs energy. Operators need to know how much, and how to run the turbine
during and after an icing event. I built **TIOCS**, the Turbine Icing Operation Control System
([AIAA 2012][doi-aiaa-2012], [PDF][pdf-aiaa-2012]). It is a fast engineering tool that couples
three codes along the blade span:

- **NASA LEWICE** for ice accretion on each blade section
- **XFOIL** for the iced airfoils' lift and drag, cross-checked with ANSYS Fluent RANS
- **XTurb-PSU**, a blade-element momentum code, for rotor performance

It was applied to the NREL Phase VI rotor and the PSU-2.5 utility-scale turbine for a rime-icing
event.

<div class="result" markdown>

- Ice accretes mostly on the **outer blade**, where the higher local speed collects more water.
- For moderate icing, power drops by **only a few percent**; prolonged events of several hours
  are expected to cost much more.
- Control changes such as higher pitch during the event, or reduced rotor speed, had little
  effect for this short event; longer events are expected to differ.

</div>

<figure markdown>
![TIOCS diagram linking ice accretion modeling, airfoil analysis and turbine performance, next to a plot of sectional blade power for clean and iced blades](../assets/figures/cp1/icing-tiocs.png)
<figcaption>TIOCS couples ice accretion, airfoil analysis and turbine performance (left).
Sectional blade power of the PSU-2.5 turbine at 12 m/s, clean vs. after 20 and 45 minutes of
icing: the loss is concentrated at the outer span (right). Jha, Brillembourg and Schmitz,
<a href="https://doi.org/10.2514/6.2012-1287">AIAA 2012-1287</a>, © the authors.</figcaption>
</figure>

## Who uses it

<div class="result" markdown>

- **Research.** UCLouvain (actuator disk tip-loss correction; mollified lifting lines, *AIAA J.*
  2018, *TCFD* 2020), Technion (LES/ALM for rotor noise and its control, AIAA SciTech 2020,
  *Aerosp. Sci. Tech.* 2021), UT Dallas (tower and nacelle effects, *Wind Energy* 2017), DTU
  (tip modeling), floating-turbine wakes (Yang et al. 2023), and the *Handbook of Wind Energy
  Aerodynamics* (2022).
- **Industry and government.** CRAFT Tech used the models in US Navy-funded simulation for
  naval pilot training ([Forsythe et al., US Navy/Boeing][pdf-forsythe]). Envision Energy uses
  them in its in-house wind-farm code.

</div>

[Compiled evidence of researcher implementations (PDF folder)][drive-impact-researchers]

## Later: from the rotor to the weather

At LLNL the question grew from one rotor to the whole atmosphere: how to drive wind-farm LES
with real mesoscale weather. That led to DOE's multi-lab coupling study
([WES 2023][doi-wes-2023]) and to [ERF](erf-exascale.md). The
[AlphaVentus repo][alphaventus-repo] holds my post-processing for a WRF-LES
generalized-actuator-disk study of the Alpha Ventus offshore farm.

## Stack

<span class="pillar">C++</span><span class="pillar">OpenFOAM</span><span class="pillar">MPI</span><span class="pillar">LES</span><span class="pillar">RANS / DES</span><span class="pillar">BEMT</span><span class="pillar">XFOIL</span><span class="pillar">Pointwise</span><span class="pillar">FieldView</span><span class="pillar">MATLAB</span><span class="pillar">Titan</span><span class="pillar">Statistics / PSD</span>

## Links

| What | Paper | PDF |
|---|---|---|
| ALM guidelines, *J. Sol. Energy Eng.* 136 (2014) | [DOI][doi-jsee-2014] | [Drive][pdf-jsee-2014] |
| Actuator curve embedding, *J. Fluid Mech.* 834 (2018) | [DOI][doi-jfm-2018] | [Drive][pdf-jfm-2018] |
| Turbulence transport in a wind farm, *Energies* 8 (2015) | [DOI][doi-energies-2015] | [Drive][pdf-energies-2015] |
| Blade-load unsteadiness, *J. Sol. Energy Eng.* 138 (2016) | [DOI][doi-jsee-2016] | [Drive][pdf-jsee-2016] |
| Accuracy of ALM, AIAA ASM 2013 | [DOI][doi-aiaa-2013] | |
| Wind-turbine and rotor-hub wakes, AHS Forum 69 (2013) | | [Drive][pdf-ahs-2013] |
| Turbulence transport in wakes, AHS Forum 70 (2014) | | [Drive][pdf-ahs-2014] |
| Turbines under icing, AIAA ASM 2012 | [DOI][doi-aiaa-2012] | [Drive][pdf-aiaa-2012] |

All papers: [Wings & Rotors folder][drive-wings-rotors] · [Google Scholar][scholar]
