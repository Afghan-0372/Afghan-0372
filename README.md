# Maxim Anisimov | Systems & Performance Engineer
### Harmonic Alignment of Logic and Hardware: C, SIMD/AVX, HPC & Low-Level Optimization

![Assembly](https://img.shields.io/badge/ASM-x86_64-red)
![SIMD](https://img.shields.io/badge/SIMD-Branchless%20Logic-red)
![C](https://img.shields.io/badge/C-00599C)

> **"I do not just write code; I act as a bridge between abstract intent and the physical reality of the Computer. My goal is to remove the noise of high-level abstractions, allowing the raw power of the hardware to flow unimpeded. I am the hands through which the Universe’s mathematical logic meets the CPU's & GPU's deterministic execution."**

### Hardware-Centric Memory Architecture
* **L1/L2 Cache Engineering:** Manual **64-byte padding** to prevent **False Sharing**. Enforcing strict `Stride-1` to neutralize **False Sharing** and optimize cache-line utilization.
* **Branchless Execution Logic:** Implementing a hardware-aware branchless predictor that dynamically adjusts execution paths based on runtime data patterns, effectively reducing pipeline stalls caused by unpredictable control flow.

### Specialized Engineering Background
* **NVIDIA DLI (Accelerated Computing):** CUDA-based kernels & Numba optimization for GPU saturation.
* **Intel HPC Curricula:** Micro-architecture tuning, manual **AVX-512** vectorization, and L1/L2 cache alignment.
* **MIT OpenCourseWare (6.172):** Systems Engineering principles — Mastering Software-Hardware Synergy.
