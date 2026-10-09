# Foundations

My degrees are in **mathematics and computing** (IIT Kharagpur, with an aerospace minor) and
**aerospace engineering** (Penn State PhD, with a computational-science minor covering parallel
computing, ML and computational linear algebra). That combination is why the same skills, not
just the same tools, serve both of my tracks. A turbulence solver and a neural network are both
large, numerically delicate programs: each needs the model derived correctly, discretized
stably, verified honestly and run efficiently at scale.

## Skills that carry across both tracks

These are what I bring regardless of the problem; the tables below show where each one came from.

- **Deriving the model.** Going from physics or data to equations: conservation laws, closures,
  rigid-body dynamics, likelihoods and loss functions.
- **Choosing and analyzing the numerics.** Discretization, stability and accuracy, and knowing
  when a scheme or an optimizer will misbehave before it does.
- **Verifying and validating.** Test problems with known answers, convergence checks,
  comparison against experiments, and held-out evaluation for ML.
- **Making it fast.** Profiling, parallel decomposition, GPU offload and memory layout, from a
  single node to tens of thousands of cores.
- **Making it reproducible.** Config-driven pipelines, regression suites, restartable runs and
  version-controlled everything.
- **Shipping it.** Production C++ on edge devices, Python services in the cloud, open-source
  releases, and documentation other people can use.
- **Explaining it.** Papers, reviews, documentation and talks for researchers, engineers and
  decision-makers.

## Mathematics

| Topic | In computational physics | In AI & ML |
|---|---|---|
| **Linear algebra** | Sparse systems, preconditioning, domain decomposition | Least-squares calibration, embeddings, transformer attention |
| **Calculus, vector and tensor analysis** | Strain-rate and stress tensors for LES on a staggered grid | Gradients and back-propagation, Jacobians for sensor fusion |
| **ODEs and dynamical systems** | 6-DOF rigid-body motion, time integration of coupled systems | Neural ODEs, motion models for vehicle tracking |
| **PDEs** | Compressible Navier–Stokes, advection–diffusion, boundary layers | PINNs, DeepONet and FNO surrogates of PDE solutions |
| **Numerical analysis** | Finite volume / difference, Runge–Kutta with acoustic sub-stepping, Roe flux, CFL limits | Conditioning and stability of training, discretization error in surrogate data |
| **Probability, statistics and stochastic processes** | Turbulence statistics, power spectra, wake meandering | Sampling of training sets, model evaluation, uncertainty in predictions |
| **Optimization** | Aitken-relaxed fluid–structure coupling, parameter calibration against measurements | Gradient-based training, camera calibration by gradient descent, hyperparameter studies |
| **Estimation and signal processing** | Spectral analysis of loads and power, filtering of noisy measurements | Kalman filtering for IMU/GPS fusion, wavelet analysis for DER detection |
| **Geometry** | Moving and adaptively refined meshes, body frames and rotations | Epipolar geometry and camera models, geospatial projections |

## Computing

| Topic | In computational physics | In AI & ML |
|---|---|---|
| **C++** | ERF core solver (CUDA), HYDRO 6-DOF coupling, OpenFOAM rotor models | Device-side detection and tracking on 100k+ vehicles (OpenCV, Eigen) |
| **Python** | Pre/post-processing, regression-test harnesses, WRF data pipelines | MLAP, collision models, LLM pipelines, geospatial data (Xarray, GDAL) |
| **Algorithms and data structures** | Block-structured AMR, mesh partitioning, staggered-grid indexing | KD-tree matching, tracking and association, data pipelines over terabytes |
| **Parallel and GPU programming** | MPI + OpenMP + CUDA, performance portability through AMReX | Data- and model-parallel training, GPU inference |
| **HPC operations** | Titan, TaihuLight, Summit, Frontier, Perlmutter; Slurm and PBS; Lustre | GPU clusters (~50k V100 cores) and AWS; storage and memory planning |
| **Data engineering** | NetCDF, GRIB and HDF; reading and reorganizing WRF output | 8 TB / 21-year datasets, geospatial rasters, labeling pipelines |
| **Software engineering** | CMake / Conan, Git workflows, regression suites, Sphinx docs | CI/CD (GitHub Actions), Docker, Kubernetes, Terraform, MLflow |

## Why this matters

- **Surrogates need a solver person.** Knowing *what* a model replaces tells you which inputs
  carry signal, which errors are unacceptable, and when the surrogate is leaving its training
  distribution. See [MLAP](ai-ml/surrogate-modeling.md).
- **Scientific software needs an ML person.** The workflows around solvers are where ML pays
  off first: picking parameters, reading logs, generating inputs. See
  [LLMs and NLP](ai-ml/llm-nlp.md).
- **Both need HPC.** The same scheduler, file-system and GPU-memory limits shape a 50k-core LES
  run and a multi-node training job.

## Aerospace breadth

Beyond CFD: flight mechanics, propulsion, structures, flight testing (climb rate, power
required, stability response to disturbances), and wind-tunnel and icing-tunnel testing. I
taught wind-tunnel testing and advanced computer programming at Penn State.

## Keeping current

I keep a public recap site of my working knowledge across these foundations:
[Study Material][studymaterial-site]. It covers computational physics, aerospace, meteorology,
machine learning, deep learning, computer vision and scientific ML.
