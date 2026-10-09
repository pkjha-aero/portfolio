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

    <span class="pillar">C++</span><span class="pillar">MPI</span><span class="pillar">OpenFOAM</span><span class="pillar">LES</span><span class="pillar">RANS / DES</span><span class="pillar">Actuator line / ACE</span><span class="pillar">BEMT</span><span class="pillar">Turbulence statistics</span><span class="pillar">Spectral analysis</span><span class="pillar">Titan</span>

    [:octicons-arrow-right-24: Read more](wings-rotors.md)

-   :material-ferry:{ .lg .middle } **Submarine maneuvering**

    ---

    A fluid–6-DOF rigid-body coupled solver on moving, adaptively refined meshes, for the
    US Navy's HYDRO code. Verified on classical flows and submarine cases.

    <span class="pillar">C++</span><span class="pillar">MPI</span><span class="pillar">Python</span><span class="pillar">RANS / LES</span><span class="pillar">6-DOF dynamics</span><span class="pillar">Fluid–structure coupling</span><span class="pillar">Mesh motion</span><span class="pillar">Unstructured AMR</span><span class="pillar">Stratified flow</span><span class="pillar">Regression testing</span><span class="pillar">CMake</span>

    [:octicons-arrow-right-24: Read more](submarine-maneuvering.md)

-   :material-weather-windy:{ .lg .middle } **ERF: GPU exascale atmospheric code**

    ---

    Core solver architecture of DOE's Energy Research and Forecasting model. C++/CUDA on AMReX,
    real-weather initialization from WRF, released on OSTI.

    <span class="pillar">C++</span><span class="pillar">CUDA</span><span class="pillar">AMReX</span><span class="pillar">MPI + OpenMP</span><span class="pillar">GPU / exascale</span><span class="pillar">Compressible Navier–Stokes</span><span class="pillar">LES / PBL</span><span class="pillar">WRF / WPS</span><span class="pillar">NetCDF</span><span class="pillar">Regression testing</span><span class="pillar">~50k cores</span>

    [:octicons-arrow-right-24: Read more](erf-exascale.md)

</div>

## Computational physics toolkit

| Area | Tools and methods |
|---|---|
| **Numerical methods** | Finite volume and finite difference, Runge–Kutta time integration with acoustic sub-stepping, Roe flux, Arakawa C-grid, block-structured and unstructured AMR, moving meshes |
| **Turbulence and physics models** | DNS, LES (Smagorinsky), RANS, DES, PBL schemes, wall models, atmospheric boundary layer, stratified flow, fluid–structure and fluid–6-DOF coupling |
| **Rotor and wing models** | Actuator line, actuator curve embedding (ACE), actuator disk, blade-element momentum theory, lifting line |
| **Codes and frameworks** | ERF, AMReX, OpenFOAM, WRF / WPS, HYDRO, ANSYS Fluent, XFOIL, NASA LEWICE, XTurb-PSU |
| **Languages** | C++, CUDA, Python, Fortran, MATLAB, Shell |
| **Parallel computing and HPC** | MPI, OpenMP, CUDA, GPU offload; Slurm and PBS; Lustre and Vast file systems |
| **Grids, data and visualization** | Pointwise, CGNS, NetCDF, HDF, GRIB; Tecplot, FieldView, VisIt, GNUPlot |
| **Software engineering** | Git, CMake, Conan, regression and unit testing, Sphinx and Doxygen documentation |
| **Experiments** | Wind-tunnel and icing-tunnel testing, flight testing |

## Computing on the world's fastest supercomputers

Since my PhD I have run my codes on some of the largest supercomputers in the world, many while
they were ranked **#1 on the [TOP500](https://www.top500.org) list**. Five of the six systems
below have held the top spot.

| Where | Supercomputer | Best TOP500 rank | My scale |
|---|---|---|---|
| Penn State | [Titan][top500-titan] (ORNL) | **#1** (Nov 2012) | ~4k CPUs, OpenFOAM LES of turbine arrays |
| CMSoft | ONR cluster | — | ~5k CPUs, submarine maneuvers |
| Envision Digital | [Tianhe-2][top500-tianhe2] | **#1** (Jun 2013 – Nov 2015) | ~5k CPUs, RANS/DES wind-resource runs |
| Envision Digital | [Sunway TaihuLight][top500-taihulight] | **#1** (Jun 2016 – Nov 2017) | ~5k CPUs, RANS/DES wind-resource runs |
| LLNL | [Summit][top500-summit] (ORNL) | **#1** (Jun 2018 – Nov 2019) | GPU atmospheric LES |
| LLNL | [Frontier][top500-frontier] (ORNL) | **#1** (Jun 2022 – Jun 2024), first exascale system | GPU atmospheric LES |
| LLNL | [Perlmutter][top500-perlmutter] (NERSC) | #5 | GPU atmospheric LES; ~50k cores across the LLNL runs |

Supercomputer links and ranks are from each system's TOP500 entry.

The same skills carry over to ML: the solvers above generate the training data for
[surrogate models](../ai-ml/surrogate-modeling.md), and their verification discipline is how I
judge whether a surrogate can be trusted.
