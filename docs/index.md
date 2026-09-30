---
title: Home
hide:
  - navigation
  - toc
---

<div class="hero" markdown>
<img class="headshot no-lightbox" src="assets/images/headshot.jpg" alt="Portrait of Pankaj Jha">
<div markdown>

# Pankaj Jha

<p class="tagline">
Computational physicist and ML engineer. I build <strong>physics simulations</strong> and the
<strong>AI that makes them fast</strong>: GPU exascale weather codes and rotor aerodynamics at
national labs, and production AI deployed on 100,000+ vehicles.
</p>

<div class="badge-row">
<span class="badge">Lawrence Livermore National Lab</span>
<span class="badge">NREL collaborator</span>
<span class="badge">US DOE · OSTI software</span>
<span class="badge">US Navy</span>
<span class="badge">AIAA Software Technical Committee</span>
</div>

</div>
</div>

**PhD in Aerospace Engineering** (Penn State; minor in computational science) and
**BS + MS in Mathematics and Computing** (IIT Kharagpur; minor in aerospace). I write the
numerics and understand the physics they model. That is the core of physics-informed ML,
surrogate modeling and digital twins.

<div class="stats">
<div class="stat"><span class="num">551</span><span class="lbl">citations · h-index 11</span></div>
<div class="stat"><span class="num">32+</span><span class="lbl">countries citing the work</span></div>
<div class="stat"><span class="num">2</span><span class="lbl">DOE OSTI software records</span></div>
<div class="stat"><span class="num">59</span><span class="lbl">merged PRs to ERF (DOE)</span></div>
<div class="stat"><span class="num">~50k</span><span class="lbl">cores on Summit / Frontier / Perlmutter</span></div>
<div class="stat"><span class="num">100k+</span><span class="lbl">devices running my vision code</span></div>
</div>

## What I bring

<div class="grid cards" markdown>

-   :material-atom-variant:{ .lg .middle } **Physics AI and surrogate models**

    ---

    ML surrogates that replace expensive transport or CFD solves: an LLNL pipeline trained on
    8 TB of atmospheric data for wildfire risk, and CFD surrogates that cut wind-resource
    assessment time by 10×. PINNs, DeepONet, FNO, PhysicsNeMo.

    [:octicons-arrow-right-24: Surrogate modeling](ai-ml/surrogate-modeling.md)

-   :material-server-network:{ .lg .middle } **Scientific software and HPC**

    ---

    Core architect of ERF, a GPU C++ atmospheric code for DOE exascale machines. Parallel C++/MPI
    rotor and submarine solvers. Regression-tested, reproducible, open source.

    [:octicons-arrow-right-24: ERF](computational-physics/erf-exascale.md)

-   :material-school-outline:{ .lg .middle } **Research credibility and community**

    ---

    14 peer-reviewed papers (JFM, JSEE, Energies, WES, JOSS). Methods adopted by groups in
    Belgium, Israel, Denmark and the US Navy. Invited talks at Stanford and NREL. Energies topic
    editor, 50+ reviews.

    [:octicons-arrow-right-24: Publications and impact](publications.md)

</div>

## Two tracks, one foundation

<div class="grid cards" markdown>

-   :material-fan:{ .lg .middle } **Computational Physics**

    ---

    - [Wings and rotors](computational-physics/wings-rotors.md): loads, wakes and atmospheric
      turbulence (Penn State, NREL)
    - [Submarine maneuvering](computational-physics/submarine-maneuvering.md): fluid–6-DOF
      coupled solver (US Navy)
    - [ERF](computational-physics/erf-exascale.md): GPU exascale atmospheric code (LLNL, DOE)

-   :material-brain:{ .lg .middle } **AI & ML**

    ---

    - [Surrogate modeling](ai-ml/surrogate-modeling.md): MLAP for wildfire (LLNL), CFD
      surrogates
    - [Vision and ADAS](ai-ml/vision-adas.md): HD maps, collision prediction, satellite CV
    - [LLMs and NLP](ai-ml/llm-nlp.md): fine-tuning, RAG, LLMs for simulation workflows

</div>

Both tracks rest on the same toolkit: C++ and Python, linear algebra, numerical analysis,
statistics and HPC. [See how they connect →](foundations.md)

**Depth and speed.** Academia and two national labs gave me depth: first-principles modeling,
verification, peer review. Startups gave me speed: shipping to 100k+ devices, and delivering for
Amazon, Hyundai and electric utilities. [More about me →](about.md)
