# Computational Physics

Ten years of building and running solvers for flows that matter to aerospace, defense and energy.
The common thread is **resolving the physics at the right scale, at an affordable cost**: blade
forces inside atmospheric turbulence, a hull responding to its own flow field, weather that
drives a wind farm.

<div class="grid cards" markdown>

-   :material-fan:{ .lg .middle } **Wings and rotors in atmospheric turbulence**

    ---

    Geometry-based actuator line and actuator curve models for wind turbines and rotorcraft,
    in OpenFOAM LES on Titan. Loads, unsteadiness, wakes. Built with NREL (now NLR); now used by
    research groups worldwide.

    <span class="pillar">C++</span><span class="pillar">OpenFOAM</span><span class="pillar">LES</span><span class="pillar">MPI</span>

    [:octicons-arrow-right-24: Read more](wings-rotors.md)

-   :material-ferry:{ .lg .middle } **Submarine maneuvering**

    ---

    A fluid–6-DOF rigid-body coupled solver on moving, adaptively refined meshes, for the
    US Navy's HYDRO code. Verified on classical flows and submarine cases.

    <span class="pillar">C++</span><span class="pillar">MPI</span><span class="pillar">AMR</span><span class="pillar">6-DOF</span>

    [:octicons-arrow-right-24: Read more](submarine-maneuvering.md)

-   :material-weather-windy:{ .lg .middle } **ERF: GPU exascale atmospheric code**

    ---

    Core solver architecture of DOE's Energy Research and Forecasting model. C++/CUDA on AMReX,
    real-weather initialization from WRF, released on OSTI.

    <span class="pillar">C++</span><span class="pillar">CUDA</span><span class="pillar">AMReX</span><span class="pillar">~50k cores</span>

    [:octicons-arrow-right-24: Read more](erf-exascale.md)

</div>

## Scale of the work

| Where | Machine | Scale |
|---|---|---|
| Penn State | Titan (ORNL) | ~4k CPUs, OpenFOAM LES of turbine arrays |
| CMSoft | ONR cluster | ~5k CPUs, submarine maneuvers |
| Envision Digital | Sunway TaihuLight, Tianhe-2 | ~5k CPUs, RANS/DES wind-resource runs |
| LLNL | Summit, Frontier, Perlmutter | ~50k cores, GPU atmospheric LES |

The same skills carry over to ML: the solvers above generate the training data for
[surrogate models](../ai-ml/surrogate-modeling.md), and their verification discipline is how I
judge whether a surrogate can be trusted.
