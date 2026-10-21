<h1 align="center">Xingtong Bao (保星彤)</h1>
<p align="center"><b>Software Engineer · C++ / Python · Simulation × AI</b> · M.S. EE, University of Pittsburgh · Shanghai</p>
<p align="center">
  <a href="mailto:18314360020@163.com"><img src="https://img.shields.io/badge/Email-18314360020%40163.com-blue?style=flat-square"/></a>
  <img src="https://img.shields.io/badge/C%2B%2B17-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/ONNX_Runtime-lightgrey?style=flat-square"/>
  <img src="https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white"/>
</p>

## About

- 4.5 years of C++ desktop-application development on **Autodesk Revit** (site & terrain modeling): triangle-mesh
  smooth shading, mesh editing, cross-model 3D point snapping, platform integration, telemetry and data validation.
- Recently built a production-style C++ wrapper for an AI thermal surrogate: interface contract, OOD detection,
  per-prediction error bounds, solver fallback, release gates, C ABI, Python pipelines.
- Interested in AI-accelerated engineering simulation: surrogates trained from solver data, embedded in C++ products.

## Featured

### [thermal-surrogate-cpp](https://github.com/xingtong-bao/thermal-surrogate-cpp) — a neural thermal surrogate, made safe to put inside a chip-design tool
C++17 · ONNX Runtime · CMake · GoogleTest · ThreadSanitizer · pybind11 · PyTorch · HotSpot · MIT · CI

Takes the public IC-ThermBench 2.5D-IC U-Net (7 input maps → 64×64 steady-state temperature field) and builds
everything a design-exploration product needs around it:

| what a product needs | what the repository shows |
|---|---|
| accurate where it has seen data | authors' baseline reproduced: MAE 1.829 K vs 1.829; PyTorch ↔ ONNX Runtime 8.2e-4 K; Python ↔ C++ bit-identical |
| knows what it does not know | configuration-novelty guard rejects 100 % of unseen chips at 1 % false rejects (per-channel range check: 20 %) |
| says how sure it is | split-conformal 90 % error bound per prediction, 1.6–3.7 K, held-out coverage 1.00 |
| never returns a confident wrong answer | surrogate → HotSpot → in-process solver fallback; unseen chips 14.8 K → 3.4 K |
| fast | 30 ms per prediction (4 CPU threads) vs 2–3 s for the solver; dynamic grids to 512² |
| safe to update | fine-tuning on 50 solver answers 17.1 K → 2.8 K; release gates caught catastrophic forgetting before it shipped |
| engineering | C ABI, pybind11, 38 GoogleTest tests, 8-thread ThreadSanitizer-clean, CI; every number traceable to a results file |

## Publication

Nonlinear manifold-learning dimensionality reduction based on adaptive density clustering —
*Journal of Chinese Computer Systems*, 2018(8). Two related invention patents.

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=xingtong-bao&show_icons=true&theme=default&hide_border=true" height="150"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=xingtong-bao&layout=compact&theme=default&hide_border=true" height="150"/>
</p>
