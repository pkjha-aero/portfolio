# ERF: GPU Exascale Atmospheric Modeling

!!! abstract "In one minute"
    - **Problem.** DOE needed a modern atmospheric model that runs on exascale GPU machines and
      bridges regional weather (mesoscale) and wind-plant turbulence (microscale). Legacy
      Fortran weather codes were not designed for GPUs.
    - **What I built.** I architected the core compressible Navier–Stokes solver of the
      **Energy Research and Forecasting (ERF)** model in C++/CUDA on AMReX, led LLNL's
      development team, and wrote the pipeline that starts ERF from real weather data (WRF/WPS).
    - **Result.** Open-source code released through DOE OSTI and published in JOSS. About 10×
      faster than traditional codes, run on ~50k cores of Summit, Frontier and Perlmutter. It
      led to **$15M in follow-up NNSA projects**.

<div class="badge-row">
<a class="badge" href="https://www.osti.gov/biblio/code-109687">OSTI code-109687</a>
<a class="badge" href="https://www.osti.gov/biblio/1998622">OSTI 1998622 · JOSS</a>
<a class="badge" href="https://github.com/erf-model/ERF">github.com/erf-model/ERF</a>
</div>

## My role

Staff scientist at **Lawrence Livermore National Laboratory** (2020–2024), and one of the first
developers of ERF. It is a DOE Wind Energy Technologies Office project across LBNL, NREL, LLNL
and ANL, with 6+ institutions involved. I led LLNL's part: strategy and development of the core
GPU solver. I'm a named developer on the [OSTI software record][osti-erf-code] and a co-author of
the [JOSS paper][doi-joss-2023].

## What ERF is

A fully compressible, non-hydrostatic atmospheric model for dry or moist air. Its features
include:

- PBL (MYNN) and LES (Smagorinsky, Deardorff) turbulence closures
- a third-order Runge–Kutta integrator with acoustic sub-stepping
- the Arakawa C-grid
- terrain-following coordinates
- microphysics

It is built on **AMReX** for block-structured adaptive mesh refinement and MPI+X parallelism,
where X is OpenMP on CPUs or CUDA / HIP / SYCL on GPUs.

```mermaid
flowchart TB
    subgraph Inputs
      W["WRF / WPS output<br/>wrfinput · wrfbdy (NetCDF)"]
      S["input_sounding<br/>(idealized profiles)"]
    end
    subgraph ERF["ERF (C++)"]
      I["Initialization &amp;<br/>lateral boundary forcing"]
      N["Compressible Navier–Stokes<br/>advection · diffusion · buoyancy"]
      T["Turbulence<br/>DNS · LES Smagorinsky · PBL"]
      B["Boundary conditions<br/>slip · no-slip · log-law wall"]
    end
    subgraph AMReX["AMReX: mesh, parallelism, I/O"]
      P["MPI + CUDA / HIP / SYCL / OpenMP"]
    end
    W --> I
    S --> I
    I --> N
    T --> N
    B --> N
    N --> P
    P --> H["Summit · Frontier · Perlmutter"]
```

## My contributions

**59 merged pull requests** from January 2021 to July 2022
([full list][erf-prs]), in four groups:

**Core solver architecture**

- The Navier–Stokes code architecture used by the rest of the team
- Advection, and momentum, thermal and scalar diffusion
- Energy and scalar diffusion in the compressible equations, and the deviatoric strain-rate tensor
- An equation-of-state fix, and a DNS implementation checked on Taylor–Green vortex and other
  problems

**Turbulence and boundary layers**

- The LES Smagorinsky model for momentum
- Slip, no-slip and **log-law wall** boundary conditions
- The atmospheric boundary-layer (ABL) driver, with channel-flow and ABL test cases seeded by
  initial perturbations

**Real-weather initialization**

This is what lets ERF start from an actual forecast.

- The **WPS–ERF interface**
- Initialization from real (`wrfinput`) and idealized meteorological data, and from `input_sounding`
- Reading WRF lateral boundary data (`wrfbdy`) with time stamps, pressure, and density from
  potential temperature
- Reorganized NetCDF I/O
- Case setups: Chisholm View (a real mesoscale case), Ekman spiral, low-level jet, Witch of Agnesi

**Quality and documentation**

- The **regression-test** framework and its documentation
- Documentation of the Euler and Navier–Stokes discretization on the Arakawa C-grid and of
  stress–strain theory
- Replacing macros with `const`, namespace fixes, and builds with terrain enabled

## Coupling across scales

Before ERF could couple mesoscale and microscale runs natively, I studied the problem with WRF-LES
and generalized actuator disks. I presented this work as first author at the AMS Annual Meeting
2023, with NREL, Virginia Tech and DTU co-authors. It also fed DOE's multi-lab lessons-learned
paper ([Haupt et al., WES 2023][doi-wes-2023]).

<figure markdown>
![Ten-minute-average wind speed in the rotor-hub plane behind a turbine, without and with the cell perturbation method](../assets/figures/cp3/wrf-les-gad-cpm.png)
<figcaption>Alpha Ventus offshore case, WRF-LES with a generalized actuator disk: 10-minute
average hub-height wind speed without (left) and with (right) the cell perturbation method
(CPM). CPM seeds realistic turbulence at the nest boundary, so the wake meanders and recovers
realistically instead of staying laminar. Jha et al., AMS 2023
(<a href="https://drive.google.com/file/d/1l0e13PglAMt-zR0Oen8r6yfPV-NlAlJt/view">slides</a>,
LLNL-PRES-843772).</figcaption>
</figure>

## Who it serves

Weather intelligence for drones, aircraft, helicopters, ships and wind farms, and nuclear
dispersion in microscale weather. ERF is now the basis for further atmospheric-physics
components (radiation, land-surface models) in DOE programs.

## Stack

<span class="pillar">C++</span><span class="pillar">CUDA</span><span class="pillar">AMReX</span><span class="pillar">MPI</span><span class="pillar">OpenMP</span><span class="pillar">NetCDF</span><span class="pillar">WRF / WPS</span><span class="pillar">LES / PBL</span><span class="pillar">Regression testing</span><span class="pillar">Sphinx</span><span class="pillar">Summit · Frontier · Perlmutter</span>

## Links

- Code: [github.com/erf-model/ERF][erf-repo] · [my merged PRs][erf-prs]
- DOE OSTI: [software record code-109687][osti-erf-code] · [JOSS record 1998622][osti-erf-joss] ·
  [OSTI software record (PDF)][pdf-osti-erf]
- Papers: [JOSS 2023][doi-joss-2023] ([PDF][pdf-joss-2023]) · [WES 2023][doi-wes-2023]
  ([PDF][pdf-wes-2023]) · [AMS 2023 slides][pdf-ams-2023]
- All: [Atmosphere & mesoscale folder][drive-atmosphere]
