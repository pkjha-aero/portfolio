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

    <span class="pillar">Python</span><span class="pillar">PyTorch</span><span class="pillar">scikit-learn</span><span class="pillar">Random forest / GB / MLP</span><span class="pillar">Feature engineering</span><span class="pillar">Parametric studies</span><span class="pillar">Pandas / NumPy</span><span class="pillar">Xarray / Dask</span><span class="pillar">NetCDF / GRIB</span><span class="pillar">GDAL / Rasterio</span><span class="pillar">JSON-driven pipelines</span><span class="pillar">Slurm / HPC</span>

    [:octicons-arrow-right-24: Read more](surrogate-modeling.md)

-   :material-car-connected:{ .lg .middle } **Computer vision and ADAS**

    ---

    Detection and tracking on 100k+ fleet devices, IMU + GPS collision prediction for Amazon
    vans, HD maps for Hyundai's autonomous-driving partner, and satellite-image solar
    detection for utilities.

    <span class="pillar">C++</span><span class="pillar">Python</span><span class="pillar">OpenCV</span><span class="pillar">Eigen</span><span class="pillar">TensorFlow</span><span class="pillar">PyTorch</span><span class="pillar">YOLO / RT-DETR</span><span class="pillar">Keypoint tracking</span><span class="pillar">Epipolar geometry</span><span class="pillar">Camera calibration</span><span class="pillar">IMU / GPS</span><span class="pillar">Kalman filtering</span><span class="pillar">SVM</span><span class="pillar">Wavelets</span><span class="pillar">Edge deployment</span>

    [:octicons-arrow-right-24: Read more](vision-adas.md)

-   :material-message-text-outline:{ .lg .middle } **LLMs and NLP**

    ---

    Fine-tuned (SFT) + RAG support chatbot for utilities. At LLNL, LLMs that turn simulation
    logs into structured data and generate solver inputs.

    <span class="pillar">Python</span><span class="pillar">PyTorch</span><span class="pillar">Transformers</span><span class="pillar">Hugging Face</span><span class="pillar">RAG</span><span class="pillar">SFT / LoRA</span><span class="pillar">RLHF / DPO</span><span class="pillar">LangChain / LangGraph</span><span class="pillar">LlamaIndex</span><span class="pillar">Vector DBs</span><span class="pillar">Prompt engineering</span><span class="pillar">LLM evaluation</span>

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

## ML and AI toolkit

The tools behind the work above, across research and production:

| Area | Tools and methods |
|---|---|
| **Languages** | Python, C++, CUDA, Shell, MATLAB |
| **ML and DL frameworks** | PyTorch, TensorFlow, scikit-learn, NVIDIA PhysicsNeMo |
| **Models** | Random forests, gradient boosting, SVMs, MLPs, CNNs, RNNs and LSTMs, GANs, diffusion models, transformers, reinforcement learning |
| **Computer vision and robotics** | OpenCV, Eigen, YOLO, RT-DETR, CLIP, keypoint detection and tracking, camera calibration, epipolar geometry, SLAM, IMU / GPS sensor fusion, Kalman filtering |
| **Generative AI and LLMs** | Transformers, Hugging Face, BERT, GPT, T5, RAG, LlamaIndex, Pinecone, ChromaDB, SFT, LoRA / PEFT, RLHF, PPO, DPO, LangChain, LangGraph, MCP, Claude and OpenAI platforms |
| **Data and geospatial** | NumPy, Pandas, Xarray, Dask, PySpark, MongoDB, NetCDF, GRIB, HDF, Zarr, GDAL, Rasterio, GeoPandas, QGIS |
| **MLOps and cloud** | Docker, Kubernetes, Terraform, GitHub Actions, MLflow, AWS (SageMaker, ECS, S3), pytest |
| **Compute** | Data- and model-parallel training on GPU clusters and AWS; Slurm; Lustre and Vast file systems |

## How I work on ML problems

**Scientific ML** (national lab):

1. **Start from the physics.** Which quantities carry signal, which scales matter, what
   conservation or symmetry the model must respect.
2. **Automate the study, not just the model.** Pipelines driven by config files, so hundreds
   of dataset × model × hyperparameter combinations can be compared rather than hand-tuned.
3. **Evaluate honestly.** Hold-out and percentile metrics, confusion matrices, comparison
   against the solver the model replaces.

**Production ML and computer vision** (industry, at NetraDyne, AZX and Envision Digital):

1. **Start from the product requirement.** What the customer needs (a collision alert, a map
   tile, a solar-capacity estimate) and how it will be judged in the field.
2. **Design for the deployment target.** Real-time C++ (OpenCV, Eigen) cross-compiled for ARM
   edge devices, or Python services in the cloud, within latency and memory budgets.
3. **Work from fleet and customer data.** Labeling and alert analysis on real-world data, with
   attention to edge cases and false alarms.
4. **Ship and support it.** Productized APIs with tests, models versioned in cloud storage,
   and KPIs tracked after release. The work reached 100,000+ devices and customers such as
   Amazon, Hyundai and electric utilities. See [industry software](../software/index.md#software-for-industry).
