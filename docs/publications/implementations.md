---
hide:
  - toc
---

# Implementation of My Mathematical Models

My wing and rotor models are mathematical models of how a blade's forces enter a flow solver:

- the geometry-based **actuator line** with an elliptic force projection
  ([JSEE 2014][doi-jsee-2014])
- the **actuator curve embedding**, ACE ([JFM 2018][doi-jfm-2018])
- the atmospheric turbulence and wake datasets and findings built with them
  ([Energies 2015][doi-energies-2015], [JSEE 2016][doi-jsee-2016])
- the **TIOCS** icing methodology ([AIAA 2012][doi-aiaa-2012])

Others have implemented them in their own codes: research groups on four continents, companies,
and US Government programs, including NASA.

<div class="stats">
<div class="stat"><span class="num">48</span><span class="lbl">independent publications building on the models</span></div>
<div class="stat"><span class="num">18</span><span class="lbl">countries</span></div>
<div class="stat"><span class="num">3</span><span class="lbl">companies: CRAFT Tech, Envision, Boeing</span></div>
<div class="stat"><span class="num">4</span><span class="lbl">US Government users: NAVAIR, ONR, DOE, NASA</span></div>
</div>

## Publications building on my models

Independent publications that implement, adopt or build on my models, sorted by year. **Excerpts**
open the highlighted passage from each paper where it uses or discusses my work; use the arrows
to step through several excerpts from the same paper.

<div class="impl-table" markdown>

| Year | Group | Their work | Publication | Excerpts |
|---|---|---|---|---|
| 2013 | **Georgia Tech, Continuum Dynamics**<br>USA | Hybrid overset CFD for unsteady aerodynamic and aeroelastic flows | IFASD 2013 | [1](../assets/excerpts/2013-quon-1.png){ .glightbox data-gallery="2013-quon" } |
| 2015 | **NAVAIR, Boeing**<br>USA | Coupled flight simulator and CFD of ship airwake (Kestrel + CASTLE) | AIAA SciTech 2015 · [link](https://doi.org/10.2514/6.2015-0556) | [1](../assets/excerpts/2015-forsythe-1.png){ .glightbox data-gallery="2015-forsythe" } · [2](../assets/excerpts/2015-forsythe-2.png){ .glightbox data-gallery="2015-forsythe" } · [3](../assets/excerpts/2015-forsythe-3.png){ .glightbox data-gallery="2015-forsythe" } · [4](../assets/excerpts/2015-forsythe-4.png){ .glightbox data-gallery="2015-forsythe" } |
| 2016 | **Iowa State University**<br>USA | Aerodynamics and loads of a dual-rotor wind turbine | *Energies* 2016 · [link](https://doi.org/10.3390/en9070571) | [1](../assets/excerpts/2016-moghadassian-1.png){ .glightbox data-gallery="2016-moghadassian" } |
| 2016 | **Penn State, CRAFT Tech**<br>USA | Coupled flight dynamics and CFD of rotorcraft–terrain interaction | AIAA MST 2016 · [link](https://doi.org/10.2514/6.2016-2136) | [1](../assets/excerpts/2016-oruc-1.png){ .glightbox data-gallery="2016-oruc" } · [2](../assets/excerpts/2016-oruc-2.png){ .glightbox data-gallery="2016-oruc" } |
| 2016 | **University of Oxford**<br>UK | Lift and drag polars from blade-resolved CFD for actuator lines | *Wind Energy* 2016 · [link](https://doi.org/10.1002/we.2065) | [1](../assets/excerpts/2016-wimshurst-1.png){ .glightbox data-gallery="2016-wimshurst" } · [2](../assets/excerpts/2016-wimshurst-2.png){ .glightbox data-gallery="2016-wimshurst" } · [3](../assets/excerpts/2016-wimshurst-3.png){ .glightbox data-gallery="2016-wimshurst" } · [4](../assets/excerpts/2016-wimshurst-4.png){ .glightbox data-gallery="2016-wimshurst" } |
| 2017 | **Penn State**<br>USA | Non-steady turbine response to daytime atmospheric turbulence | *Phil. Trans. R. Soc. A* 2017 · [link](https://doi.org/10.1098/rsta.2016.0103) | [1](../assets/excerpts/2017-nandi-1.png){ .glightbox data-gallery="2017-nandi" } · [2](../assets/excerpts/2017-nandi-2.png){ .glightbox data-gallery="2017-nandi" } · [3](../assets/excerpts/2017-nandi-3.png){ .glightbox data-gallery="2017-nandi" } · [4](../assets/excerpts/2017-nandi-4.png){ .glightbox data-gallery="2017-nandi" } |
| 2017 | **University of Limerick**<br>Ireland | Review of wind-turbine CFD, FE codes and experiments | *Prog. Aerosp. Sci.* 2017 · [link](https://doi.org/10.1016/j.paerosci.2017.05.001) | [1](../assets/excerpts/2017-obrien-1.png){ .glightbox data-gallery="2017-obrien" } · [2](../assets/excerpts/2017-obrien-2.png){ .glightbox data-gallery="2017-obrien" } · [3](../assets/excerpts/2017-obrien-3.png){ .glightbox data-gallery="2017-obrien" } · [4](../assets/excerpts/2017-obrien-4.png){ .glightbox data-gallery="2017-obrien" } |
| 2017 | **UT Dallas**<br>USA | Effect of tower and nacelle on the wake | *Wind Energy* 2017 · [link](https://doi.org/10.1002/we.2130) | [1](../assets/excerpts/2017-santoni-1.png){ .glightbox data-gallery="2017-santoni" } |
| 2018 | **UCLouvain**<br>Belgium | Actuator disk with tip-loss correction | *Wind Energy* 2018 · [link](https://doi.org/10.1002/we.2192) | [1](../assets/excerpts/2018-moens-1.png){ .glightbox data-gallery="2018-moens" } |
| 2018 | **ÉTS, Université du Québec**<br>Canada | Near wake of the actuator line in turbulent inflow (LES) | *Wind Energy Science* 2018 · [link](https://doi.org/10.5194/wes-3-905-2018) | [1](../assets/excerpts/2018-nathan-1.png){ .glightbox data-gallery="2018-nathan" } |
| 2018 | **Chongqing University**<br>China | Ice accretion and power of wind turbines | *Cold Reg. Sci. Technol.* 2018 · [link](https://doi.org/10.1016/j.coldregions.2018.01.006) | [1](../assets/excerpts/2018-shu-a-1.png){ .glightbox data-gallery="2018-shu-a" } |
| 2018 | **Chongqing University**<br>China | 3-D aerodynamics of iced wind-turbine blades | *Cold Reg. Sci. Technol.* 2018 · [link](https://doi.org/10.1016/j.coldregions.2018.01.008) | [1](../assets/excerpts/2018-shu-b-1.png){ .glightbox data-gallery="2018-shu-b" } · [2](../assets/excerpts/2018-shu-b-2.png){ .glightbox data-gallery="2018-shu-b" } |
| 2018 | **KU Leuven**<br>Belgium | Optimal dynamic induction control of inline turbines | *Phys. Fluids* 2018 · [link](https://doi.org/10.1063/1.5038600) | [1](../assets/excerpts/2018-yilmaz-1.png){ .glightbox data-gallery="2018-yilmaz" } · [2](../assets/excerpts/2018-yilmaz-2.png){ .glightbox data-gallery="2018-yilmaz" } |
| 2018 | **Harbin Engineering University, City University of London**<br>China, UK | Actuator line model of two NREL 5-MW turbine wakes | *Applied Sciences* 2018 · [link](https://doi.org/10.3390/app8030434) | [1](../assets/excerpts/2018-yu-1.png){ .glightbox data-gallery="2018-yu" } |
| 2019 | **Shahrood University of Technology**<br>Iran | Actuator line wake modeling for exergy analysis in OpenFOAM | *Int. J. Green Energy* 2019 · [link](https://doi.org/10.1080/15435075.2019.1641101) | [1](../assets/excerpts/2019-boojari-1.png){ .glightbox data-gallery="2019-boojari" } · [2](../assets/excerpts/2019-boojari-2.png){ .glightbox data-gallery="2019-boojari" } · [3](../assets/excerpts/2019-boojari-3.png){ .glightbox data-gallery="2019-boojari" } · [4](../assets/excerpts/2019-boojari-4.png){ .glightbox data-gallery="2019-boojari" } |
| 2019 | **UCLouvain**<br>Belgium | Lifting line with various mollifications, elliptical wing | *AIAA J.* 2019 · [link](https://doi.org/10.2514/1.J057487) | [1](../assets/excerpts/2019-caprace-a-1.png){ .glightbox data-gallery="2019-caprace-a" } · [2](../assets/excerpts/2019-caprace-a-2.png){ .glightbox data-gallery="2019-caprace-a" } · [3](../assets/excerpts/2019-caprace-a-3.png){ .glightbox data-gallery="2019-caprace-a" } · [4](../assets/excerpts/2019-caprace-a-4.png){ .glightbox data-gallery="2019-caprace-a" } |
| 2019 | **Universiti Teknologi Malaysia, Universiti Sains Malaysia**<br>Malaysia | Energy balance and turbulence of a Darrieus turbine | *J. Phys. Sci.* 2019 · [link](https://doi.org/10.21315/jps2019.30.1.5) | [1](../assets/excerpts/2019-hng-1.png){ .glightbox data-gallery="2019-hng" } |
| 2019 | **Johns Hopkins University**<br>USA | Filtered lifting line theory for the actuator line | *J. Fluid Mech.* 2019 · [link](https://doi.org/10.1017/jfm.2018.994) | [1](../assets/excerpts/2019-martinez-tossas-1.png){ .glightbox data-gallery="2019-martinez-tossas" } |
| 2019 | **Uppsala University, LUT**<br>Sweden, Finland | Horizontal vs. vertical axis turbines under varying roughness | *Wind Energy* 2019 · [link](https://doi.org/10.1002/we.2299) | [1](../assets/excerpts/2019-mendoza-1.png){ .glightbox data-gallery="2019-mendoza" } |
| 2020 | **Kingston University London**<br>UK | Ice accretion prediction on wind-turbine blades | AIAA SciTech 2020 · [link](https://doi.org/10.2514/6.2020-0619) | [1](../assets/excerpts/2020-abbadi-1.png){ .glightbox data-gallery="2020-abbadi" } |
| 2020 | **University of Manchester**<br>UK | Unsteady thrust on an oscillating turbine: BEM vs. actuator line | *J. Fluids Struct.* 2020 · [link](https://doi.org/10.1016/j.jfluidstructs.2020.103141) | [1](../assets/excerpts/2020-apsley-1.png){ .glightbox data-gallery="2020-apsley" } |
| 2020 | **University of New Brunswick**<br>Canada | Blade-element actuator disk for ducted tidal turbines | *Renewable Energy* 2020 · [link](https://doi.org/10.1016/j.renene.2020.02.098) | [1](../assets/excerpts/2020-baratchi-1.png){ .glightbox data-gallery="2020-baratchi" } · [2](../assets/excerpts/2020-baratchi-2.png){ .glightbox data-gallery="2020-baratchi" } |
| 2020 | **UCLouvain**<br>Belgium | Immersed lifting and dragging line for vortex particle-mesh | *Theor. Comput. Fluid Dyn.* 2020 · [link](https://doi.org/10.1007/s00162-019-00510-1) | [1](../assets/excerpts/2020-caprace-b-1.png){ .glightbox data-gallery="2020-caprace-b" } |
| 2020 | **IFP Energies nouvelles**<br>France | Super-Gaussian wake model calibrated on the near wake | TORQUE 2020 · [link](https://doi.org/10.1088/1742-6596/1618/6/062008) | [1](../assets/excerpts/2020-cathelain-1.png){ .glightbox data-gallery="2020-cathelain" } |
| 2020 | **DTU Wind Energy**<br>Denmark | A new tip correction for actuator line computations | *Wind Energy* 2020 · [link](https://doi.org/10.1002/we.2419) | [1](../assets/excerpts/2020-dag-1.png){ .glightbox data-gallery="2020-dag" } · [2](../assets/excerpts/2020-dag-2.png){ .glightbox data-gallery="2020-dag" } · [3](../assets/excerpts/2020-dag-3.png){ .glightbox data-gallery="2020-dag" } |
| 2020 | **North China Electric Power University**<br>China | Blade surface roughness and power coefficient | AIP Conf. Proc. 2020 · [link](https://doi.org/10.1063/5.0011039) | [1](../assets/excerpts/2020-jiang-1.png){ .glightbox data-gallery="2020-jiang" } · [2](../assets/excerpts/2020-jiang-2.png){ .glightbox data-gallery="2020-jiang" } |
| 2020 | **Météo-France (CNRM), University of Buenos Aires**<br>France, Argentina | Actuator line in the Meso-NH weather model, Horns Rev wind farm | *Front. Earth Sci.* 2020 · [link](https://doi.org/10.3389/feart.2019.00350) | [1](../assets/excerpts/2020-joulin-1.png){ .glightbox data-gallery="2020-joulin" } · [2](../assets/excerpts/2020-joulin-2.png){ .glightbox data-gallery="2020-joulin" } |
| 2020 | **University of Pisa, UT Dallas**<br>Italy, USA | Calibration of the actuator line for separated wakes | *Wind Energy* 2020 · [link](https://doi.org/10.1002/we.2483) | [1](../assets/excerpts/2020-rocchio-1.png){ .glightbox data-gallery="2020-rocchio" } · [2](../assets/excerpts/2020-rocchio-2.png){ .glightbox data-gallery="2020-rocchio" } |
| 2020 | **Technion**<br>Israel | Actuator line LES of rotor noise | AIAA SciTech 2020 · [link](https://doi.org/10.2514/6.2020-0035) | [1](../assets/excerpts/2020-stanly-1.png){ .glightbox data-gallery="2020-stanly" } · [2](../assets/excerpts/2020-stanly-2.png){ .glightbox data-gallery="2020-stanly" } · [3](../assets/excerpts/2020-stanly-3.png){ .glightbox data-gallery="2020-stanly" } |
| 2021 | **Technion**<br>Israel | Actuator line LES of rotor noise control | *Aerosp. Sci. Technol.* 2021 · [link](https://doi.org/10.1016/j.ast.2020.106405) | [1](../assets/excerpts/2021-delorme-1.png){ .glightbox data-gallery="2021-delorme" } · [2](../assets/excerpts/2021-delorme-2.png){ .glightbox data-gallery="2021-delorme" } · [3](../assets/excerpts/2021-delorme-3.png){ .glightbox data-gallery="2021-delorme" } |
| 2021 | **Northwestern Polytechnical University, University of Manchester**<br>China, UK | Tidal-stream turbine near wake, actuator line with turbulence corrections | Preprint (SSRN) 2021 · [link](https://doi.org/10.2139/ssrn.3906064) | [1](../assets/excerpts/2021-kang-1.png){ .glightbox data-gallery="2021-kang" } |
| 2021 | ***Handbook of Wind Energy Aerodynamics* (Springer)**<br>— | Chapter: Turbulence of Wakes | Springer 2021 · [link](https://doi.org/10.1007/978-3-030-05455-7_45-1) | [1](../assets/excerpts/2021-neunaber-1.png){ .glightbox data-gallery="2021-neunaber" } |
| 2021 | **Middle East Technical University**<br>Turkey | Wakes of tandem turbines with the actuator line | *Computers & Fluids* 2021 · [link](https://doi.org/10.1016/j.compfluid.2021.104872) | [1](../assets/excerpts/2021-onel-1.png){ .glightbox data-gallery="2021-onel" } · [2](../assets/excerpts/2021-onel-2.png){ .glightbox data-gallery="2021-onel" } · [3](../assets/excerpts/2021-onel-3.png){ .glightbox data-gallery="2021-onel" } · [4](../assets/excerpts/2021-onel-4.png){ .glightbox data-gallery="2021-onel" } |
| 2021 | **CRAFT Tech**<br>USA | ABL turbulence for ship-airwake CFD | AIAA Aviation 2021 · [link](https://doi.org/10.2514/6.2021-2481) | [1](../assets/excerpts/2021-shipman-1.png){ .glightbox data-gallery="2021-shipman" } · [2](../assets/excerpts/2021-shipman-2.png){ .glightbox data-gallery="2021-shipman" } · [3](../assets/excerpts/2021-shipman-3.png){ .glightbox data-gallery="2021-shipman" } · [4](../assets/excerpts/2021-shipman-4.png){ .glightbox data-gallery="2021-shipman" } |
| 2022 | **Beihang University**<br>China | Review: modeling the ship–helicopter dynamic interface | *Arch. Comput. Methods Eng.* 2022 · [link](https://doi.org/10.1007/s11831-022-09808-6) | [1](../assets/excerpts/2022-cao-1.png){ .glightbox data-gallery="2022-cao" } · [2](../assets/excerpts/2022-cao-2.png){ .glightbox data-gallery="2022-cao" } |
| 2022 | **Sapienza University of Rome, UT Dallas**<br>Italy, USA | Two-way coupling for aeroelastic effects in large turbines | *Renewable Energy* 2022 · [link](https://doi.org/10.1016/j.renene.2022.03.158) | [1](../assets/excerpts/2022-della-posta-1.png){ .glightbox data-gallery="2022-della-posta" } · [2](../assets/excerpts/2022-della-posta-2.png){ .glightbox data-gallery="2022-della-posta" } · [3](../assets/excerpts/2022-della-posta-3.png){ .glightbox data-gallery="2022-della-posta" } |
| 2022 | **Université de Rouen / INSA**<br>France | Rotor–wake interaction in a turbine row, multi-physics LES | TORQUE 2022 · [link](https://doi.org/10.1088/1742-6596/2265/2/022020) | [1](../assets/excerpts/2022-gremmo-1.png){ .glightbox data-gallery="2022-gremmo" } |
| 2022 | **USTC, University of São Paulo, University of Twente**<br>China, Brazil, Netherlands | Actuator line accuracy against blade-element momentum theory | *Wind Energy* 2022 · [link](https://doi.org/10.1002/we.2714) | [1](../assets/excerpts/2022-liu-1.png){ .glightbox data-gallery="2022-liu" } · [2](../assets/excerpts/2022-liu-2.png){ .glightbox data-gallery="2022-liu" } · [3](../assets/excerpts/2022-liu-3.png){ .glightbox data-gallery="2022-liu" } · [4](../assets/excerpts/2022-liu-4.png){ .glightbox data-gallery="2022-liu" } |
| 2022 | **Northumbria University**<br>UK | Hybrid control of wakes for tandem turbines | *Energy Convers. Manag.* 2022 · [link](https://doi.org/10.1016/j.enconman.2022.115575) | [1](../assets/excerpts/2022-nakhchi-1.png){ .glightbox data-gallery="2022-nakhchi" } |
| 2022 | **Technion, with NREL**<br>Israel, USA | LES of a wind turbine with a filtered actuator line | *J. Wind Eng. Ind. Aerodyn.* 2022 · [link](https://doi.org/10.1016/j.jweia.2021.104868) | [1](../assets/excerpts/2022-stanly-1.png){ .glightbox data-gallery="2022-stanly" } · [2](../assets/excerpts/2022-stanly-2.png){ .glightbox data-gallery="2022-stanly" } · [3](../assets/excerpts/2022-stanly-3.png){ .glightbox data-gallery="2022-stanly" } · [4](../assets/excerpts/2022-stanly-4.png){ .glightbox data-gallery="2022-stanly" } |
| 2022 | **NASA Ames Research Center**<br>USA | Validating actuator disk, actuator line and sliding mesh in NASA's LAVA solver | ICCFD11 2022 · [link](https://www.researchgate.net/publication/363113828) | [1](../assets/excerpts/2022-stich-1.png){ .glightbox data-gallery="2022-stich" } |
| 2022 | ***Handbook of Wind Energy Aerodynamics* (Springer)**<br>— | Chapter: CFD-Type Wake Models | Springer 2022 · [link](https://doi.org/10.1007/978-3-030-31307-4_51) | [1](../assets/excerpts/2022-witha-1.png){ .glightbox data-gallery="2022-witha" } · [2](../assets/excerpts/2022-witha-2.png){ .glightbox data-gallery="2022-witha" } · [3](../assets/excerpts/2022-witha-3.png){ .glightbox data-gallery="2022-witha" } · [4](../assets/excerpts/2022-witha-4.png){ .glightbox data-gallery="2022-witha" } |
| 2023 | **Harbin Engineering University**<br>China | Offshore turbine wakes in yaw with an improved actuator line | *J. Offshore Mech. Arct. Eng.* 2023 · [link](https://doi.org/10.1115/1.4056519) | [1](../assets/excerpts/2023-fan-1.png){ .glightbox data-gallery="2023-fan" } |
| 2023 | **KTH Royal Institute of Technology**<br>Sweden | Actuator line method for non-planar airplane wings | *AIAA J.* 2023 (arXiv 2022) · [link](https://doi.org/10.2514/1.J062398) | [1](../assets/excerpts/2023-kleine-1.png){ .glightbox data-gallery="2023-kleine" } · [2](../assets/excerpts/2023-kleine-2.png){ .glightbox data-gallery="2023-kleine" } |
| 2023 | **Shanghai Jiao Tong University, Brown University**<br>China, USA | Fluid–structure interaction of large turbines with flexible multibody dynamics | *J. Fluids Struct.* 2023 · [link](https://doi.org/10.1016/j.jfluidstructs.2023.103857) | [1](../assets/excerpts/2023-leng-1.png){ .glightbox data-gallery="2023-leng" } · [2](../assets/excerpts/2023-leng-2.png){ .glightbox data-gallery="2023-leng" } · [3](../assets/excerpts/2023-leng-3.png){ .glightbox data-gallery="2023-leng" } |
| 2023 | **Uppsala University, DTU**<br>Sweden, Denmark | Actuator line with simplified force calculation | *Wind Energy Science* 2023 · [link](https://doi.org/10.5194/wes-8-363-2023) | [1](../assets/excerpts/2023-navarro-diaz-1.png){ .glightbox data-gallery="2023-navarro-diaz" } · [2](../assets/excerpts/2023-navarro-diaz-2.png){ .glightbox data-gallery="2023-navarro-diaz" } |
| 2023 | **Harbin Engineering University**<br>China | Floating offshore turbine wakes using **ACE** | *Renewable Energy* 2023 · [link](https://doi.org/10.1016/j.renene.2023.119255) | [1](../assets/excerpts/2023-yang-1.png){ .glightbox data-gallery="2023-yang" } · [2](../assets/excerpts/2023-yang-2.png){ .glightbox data-gallery="2023-yang" } · [3](../assets/excerpts/2023-yang-3.png){ .glightbox data-gallery="2023-yang" } · [4](../assets/excerpts/2023-yang-4.png){ .glightbox data-gallery="2023-yang" } |
| 2024 | **CORIA (Normandie University), Siemens Gamesa**<br>France | Field-data validation of aero-servo-elastic LES of industrial turbines | *Wind Energy Science* 2024 · [link](https://doi.org/10.5194/wes-9-25-2024) | [1](../assets/excerpts/2024-muller-1.png){ .glightbox data-gallery="2024-muller" } · [2](../assets/excerpts/2024-muller-2.png){ .glightbox data-gallery="2024-muller" } |

</div>

Compiled first pages of many of these papers: [researcher implementations (Drive)][drive-impact-researchers].

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

Engineers at **Siemens Gamesa** (with CORIA, [WES 2024](https://doi.org/10.5194/wes-9-25-2024)) and
**Continuum Dynamics** (with Georgia Tech, IFASD 2013) have also co-authored work that builds on the
models; see the table above.

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

-   :material-rocket-launch-outline:{ .lg .middle } **NASA**

    ---

    Stich et al. of **NASA Ames Research Center** validated actuator disk, actuator line and
    sliding-mesh methods in NASA's **LAVA** solver, citing my variable-width projection that fixes
    over-predicted tip loads (ICCFD11, 2022).
    [:octicons-arrow-right-24: Excerpt](../assets/excerpts/2022-stich-1.png){ .glightbox }

-   :material-lightning-bolt:{ .lg .middle } **US Department of Energy**

    ---

    ERF and MLAP, my DOE codes released on OSTI, together with HYDRO for the Navy, are described
    on their own page.

    [:octicons-arrow-right-24: Software for US Govt](../software/us-govt.md)

</div>

Evidence: [software and rotor models for the US Government (Drive)][drive-impact-govt].
