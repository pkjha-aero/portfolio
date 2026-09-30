# Implementation of My Mathematical Models

My wing and rotor models are mathematical models of how a blade's forces enter a flow solver:

- the geometry-based **actuator line** with an elliptic force projection
  ([JSEE 2014][doi-jsee-2014])
- the **actuator curve embedding**, ACE ([JFM 2018][doi-jfm-2018])
- the atmospheric turbulence and wake datasets and findings built with them
  ([Energies 2015][doi-energies-2015], [JSEE 2016][doi-jsee-2016])
- the **TIOCS** icing methodology ([AIAA 2012][doi-aiaa-2012])

Others have implemented them in their own codes: research groups on four continents, companies,
and US Government programs.

<div class="stats">
<div class="stat"><span class="num">20+</span><span class="lbl">independent publications building on the models</span></div>
<div class="stat"><span class="num">14</span><span class="lbl">countries</span></div>
<div class="stat"><span class="num">3</span><span class="lbl">companies: CRAFT Tech, Envision, Boeing</span></div>
<div class="stat"><span class="num">3</span><span class="lbl">US Government users: NAVAIR, ONR, DOE</span></div>
</div>

## Research groups

<div class="wrap-table" markdown>

| Group | Their work | Publication |
|---|---|---|
| **UCLouvain**<br>Belgium | Actuator disk with tip-loss correction | *Wind Energy* 2018 · [DOI](https://doi.org/10.1002/we.2192) |
| **UCLouvain**<br>Belgium | Lifting line with various mollifications, elliptical wing | *AIAA J.* 2019 · [DOI](https://doi.org/10.2514/1.J057487) |
| **UCLouvain**<br>Belgium | Immersed lifting and dragging line for vortex particle-mesh | *Theor. Comput. Fluid Dyn.* 2020 · [DOI](https://doi.org/10.1007/s00162-019-00510-1) |
| **Technion**<br>Israel | Actuator line LES of rotor noise | AIAA SciTech 2020 · [DOI](https://doi.org/10.2514/6.2020-0035) |
| **Technion, with NREL**<br>Israel, USA | LES of a wind turbine with the actuator line | *J. Wind Eng. Ind. Aerodyn.* 2022 · [DOI](https://doi.org/10.1016/j.jweia.2021.104868) |
| **UT Dallas**<br>USA | Effect of tower and nacelle on the wake | *Wind Energy* 2017 · [DOI](https://doi.org/10.1002/we.2130) |
| **DTU Wind Energy**<br>Denmark | A new tip correction for actuator line computations | *Wind Energy* 2020 · [DOI](https://doi.org/10.1002/we.2419) |
| **Uppsala University, DTU**<br>Sweden, Denmark | Actuator line with simplified force calculation | *Wind Energy Science* 2023 · [DOI](https://doi.org/10.5194/wes-8-363-2023) |
| **Uppsala University, LUT**<br>Sweden, Finland | Horizontal vs. vertical axis turbines under varying roughness | *Wind Energy* 2019 · [DOI](https://doi.org/10.1002/we.2299) |
| **Sapienza University of Rome, UT Dallas**<br>Italy, USA | Two-way coupling for aeroelastic effects in large turbines | *Renewable Energy* 2022 · [DOI](https://doi.org/10.1016/j.renene.2022.03.158) |
| **University of Pisa, UT Dallas**<br>Italy, USA | Calibration of the actuator line for separated wakes | *Wind Energy* 2020 · [DOI](https://doi.org/10.1002/we.2483) |
| **Météo-France (CNRM), University of Buenos Aires**<br>France, Argentina | Actuator line in the Meso-NH weather model, Horns Rev wind farm | *Front. Earth Sci.* 2020 · [DOI](https://doi.org/10.3389/feart.2019.00350) |
| **Université de Rouen / INSA**<br>France | Rotor–wake interaction in a turbine row, multi-physics LES | TORQUE 2022 · [DOI](https://doi.org/10.1088/1742-6596/2265/2/022020) |
| **Harbin Engineering University, City University of London**<br>China, UK | Actuator line model of two NREL 5-MW turbine wakes | *Applied Sciences* 2018 · [DOI](https://doi.org/10.3390/app8030434) |
| **Harbin Engineering University**<br>China | Floating offshore turbine wakes using **ACE** | *Renewable Energy* 2023 · [DOI](https://doi.org/10.1016/j.renene.2023.119255) |
| **Chongqing University**<br>China | Ice accretion and power of wind turbines | *Cold Reg. Sci. Technol.* 2018 · [DOI](https://doi.org/10.1016/j.coldregions.2018.01.006) |
| **Chongqing University**<br>China | 3-D aerodynamics of iced wind turbine blades | *Cold Reg. Sci. Technol.* 2018 · [DOI](https://doi.org/10.1016/j.coldregions.2018.01.008) |
| **Middle East Technical University**<br>Turkey | Wakes and wake recovery of tandem turbines with the actuator line | *Computers & Fluids* 2021 · [DOI](https://doi.org/10.1016/j.compfluid.2021.104872) |
| **Shahrood University of Technology**<br>Iran | Actuator line wake modeling for exergy analysis in OpenFOAM | *Int. J. Green Energy* 2019 · [DOI](https://doi.org/10.1080/15435075.2019.1641101) |
| **Universiti Teknologi Malaysia, Universiti Sains Malaysia**<br>Malaysia | Energy balance and turbulence of a Darrieus turbine | *J. Phys. Sci.* 2019 · [DOI](https://doi.org/10.21315/jps2019.30.1.5) |

</div>

**Reference works.** Two chapters of the *Handbook of Wind Energy Aerodynamics* (Springer)
draw on the work: *CFD-Type Wake Models* ([DOI](https://doi.org/10.1007/978-3-030-31307-4_51))
and *Turbulence of Wakes* ([DOI](https://doi.org/10.1007/978-3-030-05455-7_45-1)).

Compiled first pages of these papers: [researcher implementations (Drive)][drive-impact-researchers].

## Industry

<div class="grid cards" markdown>

-   :material-helicopter:{ .lg .middle } **CRAFT Tech**

    ---

    Combustion Research and Flow Technology, Pipersville, PA, a modeling company serving the US
    Navy. It used my actuator line techniques and rotor models to model **rotorcraft flying
    through the airwake of ships at sea**, in flight simulations for **training Navy pilots**. My
    atmospheric boundary-layer datasets served as precursor data for its ship-airwake runs. The work
    was done under US Navy contracts (see [US Government](#us-government) below).

    Public evidence: Shipman and Bin (CRAFT Tech), *Atmospheric Boundary Layer Turbulence
    Simulation for Ship Airwake CFD Applications*, AIAA Aviation 2021
    ([DOI](https://doi.org/10.2514/6.2021-2481)), which builds on my turbulence work.

-   :material-wind-turbine:{ .lg .middle } **Envision Energy**

    ---

    A leading wind-turbine maker. My geometry-based actuator line guidelines were implemented in
    Envision's **in-house proprietary code** and its wind-farm simulations, and were extended to
    the actuator disk method. The findings on wake turbulence and blade-load unsteadiness fed its
    wind-resource assessment, wake analysis of operating farms, and **root-cause analysis of blade
    failures**. They also motivated in-house uncertainty-quantification work.

-   :material-airplane:{ .lg .middle } **Boeing**

    ---

    Philippe Spalart, Senior Technical Fellow at The Boeing Company, co-authored the Navy study
    below that adopted my Gaussian treatment of discrete rotor blades for coupled flight-simulator
    and CFD runs ([Forsythe et al., AIAA 2015][pdf-forsythe]).

</div>

## US Government

<div class="grid cards" markdown>

-   :material-anchor:{ .lg .middle } **NAVAIR**

    ---

    Forsythe et al. of the US Navy's **Applied Aerodynamics and Store Separation Branch** (Naval
    Air Station Patuxent River), with Boeing, coupled the DoD's HPCMP CREATE™-AV **Kestrel** CFD
    solver to the Navy's **CASTLE** flight simulator. The result is a fully coupled simulation of a
    helicopter in ship airwake. For the rotor's force source they use a Gaussian weighting of
    discrete blades, following Jha et al. (JSEE 2014).
    [AIAA 2015-0556 (PDF)][pdf-forsythe]

-   :material-ferry:{ .lg .middle } **US Navy, via CRAFT Tech**

    ---

    My models and research data were used in Navy programs contracted to CRAFT Tech for
    ship-airwake simulation and pilot training: **N00014-13-C-0456** (Office of Naval Research)
    and **N68335-16-G-0041** (Naval Air Systems Command).

-   :material-lightning-bolt:{ .lg .middle } **US Department of Energy**

    ---

    ERF and MLAP, my DOE codes released on OSTI, together with HYDRO for the Navy, are described
    on their own page.

    [:octicons-arrow-right-24: Software for US Govt](../software/us-govt.md)

</div>

Evidence: [software and rotor models for the US Government (Drive)][drive-impact-govt].
