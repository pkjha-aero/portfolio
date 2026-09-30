# Software

Software I have built, grouped by who it was built for. Industry code is proprietary, so those
entries describe what was built and link to the project pages. Everything else links to public
code or records.

| Section | What's in it |
|---|---|
| [Software for industry](#software-for-industry) | Production code at NetraDyne, Envision Digital and AZX |
| [Software for US Govt](#software-for-us-govt) | ERF and MLAP (DOE, on OSTI) and HYDRO (US Navy) |
| [Research software](#research-software) | Wind-energy research codes and analysis tools |
| [Others](#others) | Knowledge base, this site, and learning repositories |

## Software for industry

<div class="grid cards" markdown>

-   :material-car-connected:{ .lg .middle } **NetraDyne** · 2019–2020

    ---

    Fleet-safety cameras and HD maps for autonomous driving.

    - **Device-side detection and tracking** in C++ (OpenCV, Eigen): ORB keypoints matched
      under epipolar constraints, then tracked with object association. Deployed to
      **100,000+ devices**.
    - **HD maps**: lead developer. Fused IMU, GPS, camera and odometer data with Kalman
      filtering; the maps ran on Motional (Hyundai Aptiv) test cars.
    - **Collision prediction** from IMU and GPS: heuristic and SVM models, productized as an API
      with pytest coverage. Over 95% accurate, and part of the Amazon delivery-van deal.

    <span class="pillar">C++</span><span class="pillar">OpenCV</span><span class="pillar">Python</span><span class="pillar">TensorFlow</span><span class="pillar">Docker</span>

    [:octicons-arrow-right-24: Vision & ADAS](../ai-ml/vision-adas.md)

-   :material-wind-turbine:{ .lg .middle } **Envision Digital** · 2017–2019

    ---

    Wind-energy software for resource assessment on complex terrain.

    - Developed, maintained, optimized and reviewed **C++ and Python** codes for wind-resource
      assessment.
    - Made the RANS/DES CFD solver **30% faster**.
    - **ML surrogates** trained on CFD data, with a **10× speed-up**.
    - Implemented my actuator line guidelines in the in-house wind-farm code.

    <span class="pillar">C++</span><span class="pillar">MPI</span><span class="pillar">Python</span><span class="pillar">OpenFOAM</span><span class="pillar">scikit-learn</span>

    [:octicons-arrow-right-24: Surrogate modeling](../ai-ml/surrogate-modeling.md)

-   :material-transmission-tower:{ .lg .middle } **AZX** · 2024–present

    ---

    AI for electric utilities (Puget Sound Energy, Con Edison, Trilliant).

    - **Climate and weather risk** (wildfire, storms) for grid planning.
    - **Solar-panel detection** from satellite imagery (YOLO, RT-DETR) for grid-load assessment.
    - **Behind-the-meter DER detection** with wavelets and deep learning.
    - A **support chatbot** built with supervised fine-tuning and RAG.

    <span class="pillar">Python</span><span class="pillar">PyTorch</span><span class="pillar">YOLO</span><span class="pillar">LangChain</span><span class="pillar">AWS</span>

    [:octicons-arrow-right-24: Vision & ADAS](../ai-ml/vision-adas.md) ·
    [LLMs & NLP](../ai-ml/llm-nlp.md)

</div>

## Software for US Govt

Three codes built for US Government programs. Each is explained in detail on its own page.

<div class="grid cards" markdown>

-   :material-weather-windy:{ .lg .middle } **ERF** · DOE

    ---

    A GPU exascale atmospheric model, from regional weather to wind-plant turbulence, in C++/CUDA
    on AMReX. I was core solver architect and led LLNL's development; 59 merged PRs.

    [:octicons-database-16: OSTI code-109687][osti-erf-code] ·
    [:octicons-database-16: OSTI 1998622][osti-erf-joss] ·
    [:octicons-mark-github-16: erf-model/ERF][erf-repo]

-   :material-fire:{ .lg .middle } **MLAP** · DOE / LLNL

    ---

    A JSON-driven machine learning pipeline, used as a surrogate for wildfire fuel moisture
    trained on 21 years of atmospheric data. I am the sole developer.

    [:octicons-database-16: OSTI code-157408][osti-mlap] ·
    [:octicons-mark-github-16: LLNL/MLAP][llnl-mlap] ·
    [:octicons-book-16: Docs][wildfire-ml-docs]

-   :material-ferry:{ .lg .middle } **HYDRO** · US Navy

    ---

    CFD for submarine maneuvering. I built its fluid–6-DOF rigid-body coupling, restart and
    regression tests (CMSoft). Not publicly released.

</div>

[:octicons-arrow-right-24: Software for US Govt: full descriptions](us-govt.md)

## Research software

<div class="grid cards" markdown>

-   :material-wind-turbine:{ .lg .middle } **AlphaVentus**

    ---

    Post-processing for WRF-LES generalized actuator disk studies of the Alpha Ventus offshore
    wind farm (LLNL): NetCDF slices, power and line data across cases, and a parameter study.
    Python.

    [:octicons-mark-github-16: pkjha-aero/AlphaVentus][alphaventus-repo]

-   :material-grid:{ .lg .middle } **Wind_ML**

    ---

    An ML model of how mesh resolution and other simulation parameters affect how well
    wind-energy LES resolves turbulence. Contributor.

    [:octicons-mark-github-16: pkjha-aero/Wind_ML][wind-ml-repo]

-   :material-fire:{ .lg .middle } **Wildfire_ML**

    ---

    My working fork of MLAP, with the full MkDocs documentation: user guide, JSON reference,
    HPC guide and scientific assessment.

    [:octicons-mark-github-16: Repo][wildfire-ml-repo] ·
    [:octicons-book-16: Site][wildfire-ml-docs]

-   :material-fan:{ .lg .middle } **PhD research codes** · Penn State

    ---

    The actuator line with elliptic force projection, and the actuator curve embedding, in C++
    inside OpenFOAM LES; TIOCS for turbine icing (LEWICE + XFOIL + XTurb-PSU). Not publicly
    released; described in the papers.

    [:octicons-arrow-right-24: Wings & Rotors](../computational-physics/wings-rotors.md)

</div>

## Others

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **StudyMaterial**

    ---

    Recap notes across computational physics, aerospace, meteorology and ML, organized around
    ten competency pillars.

    [:octicons-mark-github-16: Repo][studymaterial-repo] ·
    [:octicons-book-16: Site][studymaterial-site]

-   :material-web:{ .lg .middle } **This portfolio**

    ---

    MkDocs Material, built and deployed by GitHub Actions, with every change reviewed through
    pull requests.

    [:octicons-mark-github-16: pkjha-aero/portfolio][portfolio-repo]

-   :material-file-document-multiple-outline:{ .lg .middle } **Publications**

    ---

    Sources for publications from my work at Envision Energy (AIAA SciTech 2018).

    [:octicons-mark-github-16: Repo][publications-repo]

-   :material-chart-bell-curve:{ .lg .middle } **AEED_Applied_Stats**

    ---

    Materials from an applied statistics workshop (2021).

    [:octicons-mark-github-16: Repo][applied-stats-repo]

</div>

**Areas I follow** (forks): NVIDIA PhysicsNeMo, nanoGPT, llm.c, openpilot, AirSim, ROS 2.
All repositories: [github.com/pkjha-aero][github]
