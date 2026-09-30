# AI & ML

I came to machine learning from simulation, so I treat models the way I treat solvers: know the
physics they are replacing, verify them against the ground truth, and scale them on real
infrastructure. The work spans **scientific ML** at a national lab and **production AI** at
startups.

<div class="grid cards" markdown>

-   :material-chart-bell-curve-cumulative:{ .lg .middle } **Surrogate modeling and Physics AI**

    ---

    MLAP, LLNL's automated pipeline that learns wildfire fuel moisture from 21 years of
    atmospheric data (released on OSTI). CFD-trained surrogates with a 10× speed-up for wind
    resource assessment.

    <span class="pillar">Python</span><span class="pillar">scikit-learn</span><span class="pillar">PyTorch</span><span class="pillar">HPC</span>

    [:octicons-arrow-right-24: Read more](surrogate-modeling.md)

-   :material-car-connected:{ .lg .middle } **Computer vision and ADAS**

    ---

    Detection and tracking on 100k+ fleet devices, IMU + GPS collision prediction for Amazon
    vans, HD maps for Hyundai's autonomous-driving partner, and satellite-image solar
    detection for utilities.

    <span class="pillar">C++</span><span class="pillar">OpenCV</span><span class="pillar">YOLO</span><span class="pillar">Sensor fusion</span>

    [:octicons-arrow-right-24: Read more](vision-adas.md)

-   :material-message-text-outline:{ .lg .middle } **LLMs and NLP**

    ---

    Fine-tuned (SFT) + RAG support chatbot for utilities. At LLNL, LLMs that turn simulation
    logs into structured data and generate solver inputs.

    <span class="pillar">Transformers</span><span class="pillar">RAG</span><span class="pillar">SFT / RLHF</span><span class="pillar">LangChain</span>

    [:octicons-arrow-right-24: Read more](llm-nlp.md)

</div>

## Physics AI toolkit

Surrogates for PDE-governed systems are where my two tracks meet. Methods I work with:

| Family | Methods | Where it fits |
|---|---|---|
| Classical surrogates | Random forests, gradient boosting, MLPs | Tabular features from simulation or reanalysis ([MLAP](surrogate-modeling.md)) |
| Physics-informed | PINNs, neural ODEs | Sparse data plus known governing equations |
| Operator learning | DeepONet, Fourier Neural Operator (FNO) | Mapping whole input fields to solution fields |
| Geometry-aware | Graph neural networks, DoMINO, GeoTransolver | CFD on complex, changing geometry (external aerodynamics) |
| Generative | Diffusion models, GANs, VAEs | Ensembles, super-resolution, synthetic weather |
| Frameworks | NVIDIA PhysicsNeMo, PyTorch, scikit-learn, TensorFlow | |

Training at scale: data-parallel and model-parallel training, GPU clusters (~50k V100 cores at
NetraDyne; Summit, Frontier and Perlmutter at LLNL), parallel file systems (Lustre, Vast), and
AWS (SageMaker, ECS).

## How I work on ML problems

1. **Start from the physics.** Which quantities carry signal, which scales matter, what
   conservation or symmetry the model must respect.
2. **Automate the study, not just the model.** Pipelines driven by config files, so hundreds
   of dataset × model × hyperparameter combinations can be compared rather than hand-tuned.
3. **Evaluate honestly.** Hold-out and percentile metrics, confusion matrices, comparison
   against the solver the model replaces.
4. **Ship it.** C++ on edge devices, Python services in the cloud, jobs on HPC schedulers.
