# Maxim Anisimov | HPC & Low-Level Python Specialist

![NumPy](https://img.shields.io/badge/NumPy-1.26+-blue)
![Numba](https://img.shields.io/badge/Numba-0.59+-green)
![HPC](https://img.shields.io/badge/HPC-Expert-orange)
![CUDA](https://img.shields.io/badge/CUDA-12.x-red)
![C++](https://img.shields.io/badge/C%2B%2B-17-blue)
![LLVM](https://img.shields.io/badge/LLVM-IR-purple)
![Assembly](https://img.shields.io/badge/ASM-x86_64-red)

> **Philosophy:** Python is a remote control for LLVM kernels. Zero overhead in hot paths.

## Technical Stack (Strictly Typed & Pre-allocated)
*   **Compute:** Numba (@njit, @parallel), NumPy (Structured Arrays, memmap), CUDA (PyCUDA).
*   **Memory:** Explicit Memory Management (`ctypes`, `np.memmap`), Structured Arrays, Cache Line Alignment.
*   **Optimization:** SIMD Vectorization (AVX-512/SSE), L1/L2 Cache Locality, Stride-1 Access, Branch Prediction Avoidance.
*   **Architecture:** C/Fortran memory layout (`order='C'`/`F`), Manual Memory Management, LLVM IR Inspection.

### Performance Credentials
*   [Scientific Computing with Python](https://freecodecamp.org/certification/maximanisimov/python-v9) | freeCodeCamp
*   **Focus**: Eliminating Python Object Overhead in Data Pipelines.
*   **Profiling:** `cProfile`, `line_profiler`, `numba.cuda.profiler`, `valgrind/memcheck`.
*   **Benchmarking:** Micro-benchmarking with `time.perf_counter()`, latency measurement, and memory profiling (`tracemalloc`).

🚀 System Principles: The Zero-Overhead Architecture
"Python is the glue; Numba/LLVM is the engine. We build engines that run at C speed."

HOT PATH SANITIZATION:

Prohibition of Dynamic Allocation: Strict ban on list.append(), dicts, and object creation inside JIT scopes.
Immutable Buffers: All working sets are pre-allocated at t=0 with fixed capacity to eliminate heap fragmentation overhead.
STRICT TYPE SIGNATURES (LLVM IR Level):

Zero Runtime Dispatch: Explicit dtype declarations (np.float64, np.int32) prevent the JIT compiler from generating type-checking bytecode.
No Any: Eliminates dynamic typing overhead, forcing the compiler to generate pure machine code (x86_64/AVX-512).
BRANCH ELIMINATION & PREDICTION OPTIMIZATION:

Deterministic Control Flow: Critical loops use arithmetic masking or conditional moves (cmov) instead of if/else to ensure perfect branch prediction and enable full SIMD vectorization (SSE/AVX).
MEMORY CONTIGUITY & CACHE HIERARCHY:

Stride-1 Access Guarantee: All data passed to kernels is C-contiguous (order='C') or manually stride-calculated to ensure sequential memory access.
Cache Line Alignment: Data structures are padded to 64-byte boundaries (L1 cache line) to maximize spatial locality and throughput.
ARCHITECTURAL ABSTRACTION LAYER:
Python acts strictly as a Remote Control. All heavy lifting is offloaded to compiled kernels (@njit, PyCUDA). No Python objects traverse the boundary between interpreter and kernel.

