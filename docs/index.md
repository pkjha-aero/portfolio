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
Computational physicist and ML engineer. I build <strong>physics simulations</strong>, the
<strong>AI that makes them fast</strong>, and <strong>production computer vision and ML
software</strong>: GPU exascale weather codes at national labs, and AI shipped by startups to
100,000+ vehicles and to electric utilities.
</p>

<div class="badge-row">
<span class="badge">Lawrence Livermore National Lab</span>
<span class="badge">NREL collaborator</span>
<span class="badge">US DOE · OSTI software</span>
<span class="badge">US Navy</span>
<span class="badge">Production AI: NetraDyne · Envision · AZX</span>
<span class="badge">AIAA Software Technical Committee</span>
</div>

</div>
</div>

<span class="em-title">PhD in Aerospace Engineering</span> (**Penn State; minor in computational science**) and
<span class="em-title">BS + MS in Mathematics and Computing</span> (**IIT Kharagpur; minor in aerospace**). I write the
numerics and understand the physics they model, which is the core of physics-informed ML,
surrogate modeling and digital twins. About seven years of my career have been in industry,
writing production <span class="em-title">C++</span> and <span class="em-title">Python</span> for <span class="em-title">computer vision</span>, <span class="em-title">ML</span> and <span class="em-title">CFD</span>, next to four years at
Lawrence Livermore.

<div class="stats">
<div class="stat"><span class="num">100k+</span><span class="lbl">devices running my computer vision code</span></div>
<div class="stat"><span class="num">2</span><span class="lbl">US Govt (DOE) OSTI software records</span></div>
<div class="stat"><span class="num">59</span><span class="lbl">merged PRs to ERF (DOE)</span></div>
<div class="stat"><span class="num">~50k</span><span class="lbl">cores on Summit / Frontier / Perlmutter supercomputers</span></div>
<div class="stat"><span class="num">551</span><span class="lbl">citations · h-index 11</span></div>
<div class="stat"><span class="num">34</span><span class="lbl">countries &amp; regions citing the work</span></div>
</div>

## What I bring

<div class="grid cards two-up" markdown>

-   :material-atom-variant:{ .lg .middle } **Physics AI and surrogate models**

    ---

    - **MLAP** (LLNL): surrogate for wildfire fuel moisture, trained on 8 TB and 21 years of
      atmospheric data
    - **CFD surrogates** (Envision): wind-resource assessment 10× faster
    - Physics AI toolkit: PINNs, DeepONet, FNO, NVIDIA PhysicsNeMo

    [:octicons-arrow-right-24: Surrogate modeling](ai-ml/surrogate-modeling.md)

-   :material-eye-outline:{ .lg .middle } **Computer Vision and AI/ML Software**

    ---

    - **Detection and tracking** in C++ running on **100,000+** fleet devices (NetraDyne)
    - **Collision prediction** (>95%) behind an Amazon fleet deal; **HD maps** behind a $10M
      Hyundai investment
    - **Satellite CV** for solar-panel detection and **DER detection** for utilities (AZX)
    - **LLM software**: SFT + RAG chatbot; LLM pipelines for simulation logs and inputs

    [:octicons-arrow-right-24: Vision & ADAS](ai-ml/vision-adas.md) ·
    [LLMs & NLP](ai-ml/llm-nlp.md) ·
    [Industry software](software/index.md#software-for-industry)

-   :material-server-network:{ .lg .middle } **Scientific software and HPC**

    ---

    - **Core architect of ERF**, DOE's GPU exascale atmospheric code (C++/CUDA, AMReX); 59 merged
      PRs; ~50k cores
    - Parallel C++/MPI **rotor** (OpenFOAM) and **submarine** (US Navy HYDRO) solvers
    - Regression-tested and reproducible; released on DOE OSTI

    [:octicons-arrow-right-24: ERF](computational-physics/erf-exascale.md) ·
    [Software for US Govt](software/us-govt.md)

-   :material-school-outline:{ .lg .middle } **Research credibility and community**

    ---

    - **14 peer-reviewed papers** (JFM, JSEE, Energies, WES, JOSS); 551 citations
    - Models built on by **48 publications from 18 countries**, by industry, NAVAIR and NASA
    - Invited talks at Stanford and NREL; Energies topic editor; 50+ reviews

    [:octicons-arrow-right-24: Publications](publications/index.md) ·
    [Implementations](publications/implementations.md)

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
      surrogates (Envision)
    - [Vision and ADAS](ai-ml/vision-adas.md): on-device tracking, HD maps, collision
      prediction (NetraDyne); satellite CV (AZX)
    - [LLMs and NLP](ai-ml/llm-nlp.md): fine-tuning, RAG, LLMs for simulation workflows

</div>

Both tracks rest on the same toolkit: C++ and Python, linear algebra, numerical analysis,
statistics and HPC. [See how they connect →](foundations.md)

## Depth and speed

<div class="grid cards" markdown>

-   :material-layers-triple-outline:{ .lg .middle } **Depth: academia and national labs**

    ---

    - First-principles models of wings and rotors, implemented by groups worldwide
    - Verification and validation against theory and experiment
    - Open-source DOE codes on exascale machines (LLNL; NREL collaboration)
    - Peer review, editorial work, and the AIAA Software Technical Committee

-   :material-rocket-launch-outline:{ .lg .middle } **Speed: startups and industry**

    ---

    - Production computer vision on **100,000+** devices (NetraDyne)
    - Models behind an **Amazon** fleet deal and a **$10M Hyundai** investment
    - **10×** CFD surrogates and a **30%** faster solver (Envision)
    - AI for electric utilities: climate risk, satellite CV, LLMs (AZX)

</div>

[More about me →](about.md)
