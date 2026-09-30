# Foundations

My degrees are in **mathematics and computing** (IIT Kharagpur, with an aerospace minor) and
**aerospace engineering** (Penn State PhD, with a computational-science minor covering parallel
computing, ML and computational linear algebra). That combination is why the same toolkit
serves both of my tracks. A turbulence solver and a neural network are both large, sparse,
numerically delicate programs that need the same care.

## One toolkit, two tracks

| Foundation | In computational physics | In AI & ML |
|---|---|---|
| **C++** | ERF core solver (CUDA), HYDRO 6-DOF coupling, OpenFOAM rotor models | Device-side detection and tracking on 100k+ vehicles (OpenCV, Eigen) |
| **Python** | Pre/post-processing, regression-test harnesses, WRF data pipelines | MLAP, collision models, LLM pipelines, geospatial data (Xarray, GDAL) |
| **Linear algebra** | Implicit solvers, preconditioning, domain decomposition | Camera geometry (epipolar constraints), calibration by optimization, transformer attention |
| **Numerical analysis and PDEs** | Finite volume / difference, Runge–Kutta with acoustic sub-stepping, the Arakawa C-grid | Neural operators and PINNs, stability of training, surrogates of PDE solutions |
| **Probability and statistics** | Turbulence statistics, power spectra, wake recovery | Sampling for training sets, model evaluation, uncertainty |
| **Estimation and optimization** | Fluid–structure coupling (Aitken relaxation), calibration against measurements | Kalman filtering and sensor fusion, gradient descent, hyperparameter studies |
| **HPC** | MPI + OpenMP + CUDA on Titan, TaihuLight, Summit, Frontier, Perlmutter | Data- and model-parallel training on GPU clusters and AWS |
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
