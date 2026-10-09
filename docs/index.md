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
<span class="badge">NLR (formerly NREL) collaborator</span>
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
surrogate modeling and digital twins.

I have more than seven years of industry experience, writing production <span class="em-title">C++</span> and
<span class="em-title">Python</span>: <span class="em-title">computer vision</span> and <span class="em-title">ML</span> at startups (Envision Digital, NetraDyne, AZX),
and <span class="em-title">CFD</span> for the US Navy at a DoD contractor (CMSoft). My national-lab experience includes
PhD research in collaboration with NREL (now the National Laboratory of the Rockies, NLR),
followed by four years of post-PhD work at Lawrence Livermore covering both computational
physics and ML. Since my PhD, I have written and run parallel codes, for both simulation and ML training, on some of the [world's fastest supercomputers](computational-physics/index.md#computing-on-the-worlds-fastest-supercomputers): five have been #1 on the TOP500 list, including Frontier, the first exascale system.

<div class="stats" markdown>
<div class="stat" markdown>
<span class="num">100k+</span>
[edge devices running my computer vision code](ai-ml/vision-adas.md#netradyne){ .lbl }
</div>
<div class="stat" markdown>
<span class="num">2</span>
[US Govt (DOE) OSTI software records](software/us-govt.md){ .lbl }
</div>
<div class="stat" markdown>
<span class="num">59</span>
[merged PRs to ERF (DOE)](computational-physics/erf-exascale.md#my-contributions){ .lbl }
</div>
<div class="stat" markdown>
<span class="num">~50k</span>
[cores on Summit / Frontier / Perlmutter supercomputers](computational-physics/index.md#computing-on-the-worlds-fastest-supercomputers){ .lbl }
</div>
<div class="stat" markdown>
<span class="num">554</span>
[citations · h-index 11](https://scholar.google.com/citations?user=VRaAAkgAAAAJ&hl=en){ .lbl }
</div>
<div class="stat" markdown>
<span class="num">34</span>
[countries &amp; regions citing the work](publications/index.md#where-the-citations-come-from){ .lbl }
</div>
</div>
</div>

## What I bring

<div class="grid cards two-up" markdown>

-   :material-atom-variant:{ .lg .middle } **Physics AI and surrogate models**

    ---

    - **MLAP** (LLNL): surrogate for wildfire fuel moisture, trained on 8 TB and 21 years of
      atmospheric data
    - **CFD surrogates** (Envision): wind-resource assessment 10× faster
    - **Physics AI toolkit**: PINNs, DeepONet, FNO, NVIDIA PhysicsNeMo

    [:octicons-arrow-right-24: Surrogate modeling](ai-ml/surrogate-modeling.md)

-   :material-eye-outline:{ .lg .middle } **Computer Vision and AI/ML Software**

    ---

    - **Detection and tracking** in C++ running on **100,000+** fleet devices (NetraDyne)
    - **Collision prediction** (>95%) behind an Amazon fleet deal; **HD maps** behind a $10M
      Hyundai investment
    - **Satellite CV** for solar-panel detection and **DER detection** for utilities (AZX)
    - **LLM software**: SFT + RAG chatbot; LLM pipelines for simulation logs and inputs

    [:octicons-arrow-right-24: Computer Vision & ADAS](ai-ml/vision-adas.md) ·
    [LLMs & NLP](ai-ml/llm-nlp.md) ·
    [Industry software](software/index.md#software-for-industry)

-   :material-server-network:{ .lg .middle } **Scientific software and HPC/ Supercomputing**

    ---

    - **Core architect of ERF**, DOE's GPU exascale atmospheric code (C++/CUDA, AMReX); 59 merged
      PRs; ~50k cores; [~5×- 15x faster than WRF depending on problems](computational-physics/erf-exascale.md#performance-relative-to-wrf)
    - **Parallel C++/MPI** solvers for [**rotors**](computational-physics/wings-rotors.md) (OpenFOAM) and
      [**submarine maneuvering**](computational-physics/submarine-maneuvering.md) (US Navy HYDRO)
    - Regression-tested and reproducible; released on DOE OSTI

    [:octicons-arrow-right-24: ERF](computational-physics/erf-exascale.md) ·
    [Submarine maneuvering](computational-physics/submarine-maneuvering.md) ·
    [Software for US Govt](software/us-govt.md)

-   :material-school-outline:{ .lg .middle } **Research credibility and community**

    ---

    - **14 peer-reviewed papers** (JFM, JSEE, Energies, WES, JOSS); 554 citations
    - Models built on by **48 publications from 18 countries**, by industry, NAVAIR and NASA
    - Invited talks at Stanford and NREL (now NLR); Energies topic editor; 50+ reviews

    [:octicons-arrow-right-24: Publications](publications/index.md) ·
    [Implementations](publications/implementations.md)

</div>

## Two tracks, one foundation

<div class="grid cards" markdown>

-   :material-fan:{ .lg .middle } **Computational Physics**

    ---

    - [Wings and rotors](computational-physics/wings-rotors.md): loads, wakes and atmospheric
      turbulence (Penn State, NREL/NLR)
    - [Submarine maneuvering](computational-physics/submarine-maneuvering.md): fluid–6-DOF
      coupled solver (US Navy)
    - [ERF](computational-physics/erf-exascale.md): GPU exascale atmospheric code (LLNL, DOE)

-   :material-brain:{ .lg .middle } **AI & ML**

    ---

    - [Surrogate modeling](ai-ml/surrogate-modeling.md): MLAP for wildfire (LLNL), CFD
      surrogates (Envision)
    - [Computer vision and ADAS](ai-ml/vision-adas.md): on-device tracking, HD maps, collision
      prediction (NetraDyne); satellite CV (AZX)
    - [LLMs and NLP](ai-ml/llm-nlp.md): fine-tuning, RAG, LLMs for simulation workflows

</div>

Both tracks rest on the same skills and toolkit:

- **Skills:** deriving the model from first principles, choosing and analyzing the numerics,
  verifying and validating, making it fast at scale, making it reproducible, and shipping it.
- **Mathematics:** linear algebra; calculus, vector and tensor analysis; ODEs and PDEs;
  numerical analysis; probability, statistics and stochastic processes; optimization;
  estimation and signal processing; geometry.
- **Computing:** C++ and Python; algorithms and data structures; parallel and GPU programming;
  HPC; data engineering; software engineering.

[See how they connect →](foundations.md)

## Depth and speed

<div class="grid cards" markdown>

-   :material-layers-triple-outline:{ .lg .middle } **Depth: academia and national labs**

    ---

    - First-principles models of wings and rotors, implemented by groups worldwide
    - Verification and validation against theory and experiment
    - Open-source DOE codes on exascale machines (LLNL; NREL/NLR collaboration)
    - Peer review, editorial work, and the AIAA Software Technical Committee

-   :material-rocket-launch-outline:{ .lg .middle } **Speed: startups and industry**

    ---

    - Production computer vision on **100,000+** devices (NetraDyne)
    - Models behind an **Amazon** fleet deal and a **$10M Hyundai** investment
    - **10×** CFD surrogates and a **30%** faster solver (Envision)
    - AI for electric utilities: climate risk, satellite CV, LLMs (AZX)

</div>

[More about me →](about.md)
