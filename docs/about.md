# About

## The short version

I work where physics simulation meets machine learning. My training is in both fields:
**mathematics and computing** at IIT Kharagpur, then a **PhD in aerospace engineering** at
Penn State. That means I can derive the model, write the solver, scale it on a supercomputer,
and train the surrogate that replaces it when thousands of runs are needed.

My work is not limited to national labs and scientific code. It has two sides
([Depth and speed](#depth-and-speed)):

- **Depth and foundations**, from academia and four years at Lawrence Livermore:
  first-principles [wing and rotor models](computational-physics/wings-rotors.md#the-modeling-problem)
  implemented by [groups worldwide](publications/implementations.md#publications-building-on-my-models), the
  [core solver of ERF](computational-physics/erf-exascale.md#my-contributions) on DOE exascale
  machines, [verification and validation](computational-physics/submarine-maneuvering.md#verification-and-validation),
  and the [shared mathematical toolkit](foundations.md#one-toolkit-two-tracks) behind both
  physics and ML.
- **Production code at a high pace**, from about seven years in industry writing production C++
  and Python: computer vision on 100,000+ devices at [NetraDyne](ai-ml/vision-adas.md#netradyne),
  [CFD surrogates and solver speed-ups](ai-ml/surrogate-modeling.md#earlier-cfd-surrogates-at-envision-digital)
  at Envision Digital, the [fluid–6-DOF coupling](computational-physics/submarine-maneuvering.md#how-the-coupling-works)
  for the US Navy at CMSoft, and [grid AI](ai-ml/vision-adas.md#azx) and an
  [LLM chatbot](ai-ml/llm-nlp.md#support-chatbot-azx) at AZX. See all
  [industry software](software/index.md#software-for-industry).

### Application areas

- **Aerospace**: aircraft wings, [helicopters and rotor hubs](computational-physics/wings-rotors.md#rotorcraft-the-wake-of-a-helicopter-rotor-hub),
  drones and UAVs, jet engines, and [ship airwakes](publications/implementations.md#us-government)
  for Navy pilot training
- **Naval**: [submarine maneuvering](computational-physics/submarine-maneuvering.md)
- **Energy**: [wind turbines and wind farms](computational-physics/wings-rotors.md),
  [turbine icing](computational-physics/wings-rotors.md#icing-turbines-in-cold-climates), and
  [electric grids and distributed energy](ai-ml/vision-adas.md#azx)
- **Weather and climate**: [mesoscale-to-microscale atmosphere](computational-physics/erf-exascale.md),
  weather intelligence for aviation and shipping, [wildfire risk](ai-ml/surrogate-modeling.md),
  climate change, earth-system modeling, and geospatial intelligence
- **Autonomous driving and robotics**: [ADAS, HD maps and collision prediction](ai-ml/vision-adas.md#netradyne)
- **Scientific workflows**: [LLMs for simulation logs and inputs](ai-ml/llm-nlp.md#llms-for-simulation-workflows-llnl)

### Stakeholders served

- **US Government**: Department of Energy (DOE), National Nuclear Security Administration
  (NNSA), Department of Defense (DoD), US Navy and US Army
- **Industry**: GE Aerospace, Envision, Hyundai (Motional), Amazon, Puget Sound Energy, Con
  Edison and Trilliant
- **Research community**: national laboratories and universities, AIAA and the Vertical Flight
  Society (VFS), and the aerospace, rotorcraft, wind-energy and meteorology communities

## Two national labs

<div class="grid cards" markdown>

-   **Lawrence Livermore National Laboratory**, *staff scientist, 2020–2024*

    ---

    Architected the core GPU solver of [ERF](computational-physics/erf-exascale.md) and led
    LLNL's development team in a collaboration of 6+ institutions (LBNL, NREL, ANL and others).
    The work led to $15M in follow-up NNSA projects. Built
    [MLAP](ai-ml/surrogate-modeling.md), LLNL's machine learning automation pipeline for wildfire
    fuel moisture. Both are released on DOE's OSTI.

-   **National Renewable Energy Laboratory (NREL)**, *collaborator*

    ---

    During my PhD I co-authored the actuator-line modeling guidelines with NREL researchers
    (JSEE 2014, now my most-cited paper), and gave an invited talk at the National Wind
    Technology Center. At LLNL I continued the collaboration through ERF and DOE's
    mesoscale–microscale coupling effort.

</div>

## Depth and speed

<div class="grid cards" markdown>

-   :material-layers-triple-outline:{ .lg .middle } **Depth: academia and national labs**

    ---

    - First-principles models of wings and rotors, implemented by research groups worldwide and
      cited from 32+ countries
    - Verification and validation against theory and experiment
    - Open-source codes on DOE exascale machines
    - Peer review for Wind Energy, JSEE and AIAA SciTech; Energies topic editor

-   :material-rocket-launch-outline:{ .lg .middle } **Speed: startups and industry**

    ---

    - Computer vision shipped to **100,000+ devices** (NetraDyne)
    - Collision prediction behind an **Amazon** delivery-van deal; HD maps behind a **$10M
      Hyundai** investment
    - CFD surrogates with a **10× speed-up** and a 30% faster solver (Envision Digital)
    - Climate risk, satellite computer vision and LLM software for electric utilities (AZX)

</div>

## Timeline

<div class="timeline" markdown>

**AZX PBC** <span class="when">2024 – present</span>
:   Staff Machine Learning Engineer. Weather and climate risk for grid planning (wildfire,
    storms); satellite-image solar panel detection; behind-the-meter DER detection; an SFT + RAG
    support chatbot. For Puget Sound Energy, Con Edison and Trilliant.

**Lawrence Livermore National Laboratory** <span class="when">2020 – 2024</span>
:   Staff Scientist (ML, computer vision, fluid dynamics). ERF core solver (C++/CUDA, ~50k
    cores); MLAP (8 TB, 21 years of data); YOLO-based lab-equipment tracking; LLM log parsing and
    input generation.

**NetraDyne** <span class="when">2019 – 2020</span>
:   Staff Engineer (computer vision, robotics, ML). ADAS detection and tracking in C++/OpenCV
    on 100k+ devices; IMU + GPS collision prediction (>95% accuracy); lead developer of HD maps.

**Envision Digital** (now Univers) <span class="when">2017 – 2019</span>
:   Senior Engineer (ML, supercomputing, fluid dynamics). ML surrogates trained on CFD (10×
    speed-up); 30% faster RANS/DES solver; wind-resource assessment on complex terrain.

**CMSoft** <span class="when">2015 – 2017</span>
:   Research Scientist (supercomputing, fluid dynamics). Fluid–6-DOF coupled solver for
    submarine maneuvers for the US Navy.

**The Pennsylvania State University** <span class="when">2010 – 2015</span>
:   PhD research and teaching. Geometry-based wing and rotor models, turbulence statistics,
    OpenFOAM LES on Titan; taught wind-tunnel testing and advanced programming; flight testing.

**IIT Kharagpur**
:   BS + MS in Mathematics and Computing (computer science, mathematics, statistics); minor in
    aerospace engineering.

</div>

## Beyond the day job

I keep a public recap site of my working knowledge across computational physics, aerospace,
meteorology and ML: [Study Material][studymaterial-site]. I'm a member of AIAA's Software
Technical Committee and the ASME Wind Energy Technical Committee, and was invited to serve as
an official nominator for the VinFuture Prize (2023).
