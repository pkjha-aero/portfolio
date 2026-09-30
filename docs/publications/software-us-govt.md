# Software for US Govt

Three codes I built or co-built for US Government programs: two released by the Department of
Energy and recorded on its Office of Scientific and Technical Information (**OSTI**), and one
developed for the **US Navy**.

| Code | Sponsor | What it does | My role | Public record |
|---|---|---|---|---|
| **ERF** | DOE Wind Energy Technologies Office | GPU exascale atmospheric model, from weather to wind-plant scale | Core solver architect; led LLNL development | [OSTI code-109687][osti-erf-code] · [OSTI 1998622 (JOSS)][osti-erf-joss] |
| **MLAP** | DOE / LLNL | Automated ML pipeline; surrogate for wildfire fuel moisture | Sole developer | [OSTI code-157408][osti-mlap] |
| **HYDRO** | US Navy | CFD for submarine maneuvering, with fluid–6-DOF coupling | Developed the rigid-body coupling (CMSoft) | Not publicly released |

## ERF: Energy Research and Forecasting

<div class="badge-row">
<a class="badge" href="https://www.osti.gov/biblio/code-109687">OSTI code-109687</a>
<a class="badge" href="https://www.osti.gov/biblio/1998622">OSTI 1998622</a>
<a class="badge" href="https://github.com/erf-model/ERF">github.com/erf-model/ERF</a>
</div>

**What it is.** A next-generation regional atmospheric model for mesoscale and microscale flows.
It solves the fully compressible Navier–Stokes equations for dry or moist air, with advection,
diffusion, turbulence (PBL and LES), terrain and moisture physics. It is built on AMReX and runs
with MPI+X, where X is OpenMP on CPUs or CUDA, HIP or SYCL on GPUs, so the same code runs on
CPU-only systems and on DOE's GPU exascale machines.

**Why DOE funded it.** Wind plants sit inside weather. ERF bridges regional weather and the
turbulence a wind farm actually sees, so it can serve both as a forecast model and as a test bed
for physics and numerics. The same capability supports weather intelligence for aviation,
shipping and dispersion studies.

**Records.**

- **OSTI code-109687**: *Energy Research and Forecasting (ERF) v1*, released 29 June 2022 by
  LBNL, NREL, LLNL and ANL under a BSD-3 license. I am a named developer.
- **OSTI 1998622**: the *Journal of Open Source Software* paper (2023,
  [doi:10.21105/joss.05202][doi-joss-2023]). I am a co-author.

**My part.** I was one of ERF's first developers and architected its core solver: the
Navier–Stokes code architecture, advection and diffusion, LES and wall models, the ABL driver,
real-weather initialization from WRF, and the regression tests. I led LLNL's development team in
a collaboration of 6+ institutions, and the work led to $15M in follow-up NNSA projects.
[Full ERF page →](../computational-physics/erf-exascale.md)

## MLAP: Machine Learning Automation Pipeline

<div class="badge-row">
<a class="badge" href="https://www.osti.gov/biblio/code-157408">OSTI code-157408</a>
<a class="badge" href="https://github.com/LLNL/MLAP">github.com/LLNL/MLAP</a>
<a class="badge" href="https://pkjha-aero.github.io/Wildfire_ML/">Documentation</a>
</div>

**What it is.** A Python framework that runs a machine learning study step by step: extract
data, prepare features and labels, train, evaluate many models side by side, and predict. Each
step is driven by a JSON file, so hundreds of cases run from one command without editing code.

**Why it matters.** Its first application predicts wildfire fuel moisture from 21 years of
atmospheric history (8 TB). It is a cheap surrogate for transport-based models, so risk planners
can explore many scenarios instead of a handful. The design is general: any target variable that
depends on the history of its drivers on a space-time grid fits the same pipeline.

**Record.** **OSTI code-157408**: *Machine Learning Automation Pipeline*, released 18 September
2024 by LLNL under the MIT license. I am the sole developer.
[Full MLAP page →](../ai-ml/surrogate-modeling.md)

## HYDRO: submarine maneuvering for the US Navy

**What it is.** HYDRO is a US Navy computational fluid dynamics code for underwater vehicles. It
is parallel C++ with MPI, uses unstructured, adaptively refined meshes that move with the body,
and offers RANS and LES turbulence models.

**My part.** At CMSoft (2015–2017) I developed the **fluid–6-DOF rigid-body coupling** that lets
HYDRO simulate a submarine maneuvering under its own hydrodynamic loads:

- a multi-component rigid-body system, with loads summed to the center of gravity
- forced (prescribed) and free (coupled) motion
- stable fluid–body sub-iteration with Aitken relaxation
- full restart of coupled runs
- the regression-test suite used to verify the code on classical flows and submarine cases

It ran on the ONR cluster at about 5,000 CPUs.

**Public record.** HYDRO is not publicly released, so there is no OSTI record or code link. This
description stays at the level of general capabilities.
[Full submarine page →](../computational-physics/submarine-maneuvering.md)

## Evidence

- [Software and rotor models for the US Government (Drive folder)][drive-impact-govt], which
  includes the [DOE OSTI software record (PDF)][pdf-osti-erf]
