# Quant Kernel (`Qκ`)

**Foundational primitives for quantitative finance, market microstructure, and low-latency execution.**

Quant Kernel develops deterministic, zero-overhead financial libraries bridging continuous-time mathematical finance ($\mathbb{Q}$-measure pricing, risk sensitivities, and stochastic control) with bare-metal systems engineering (lock-free C++20/23 kernels, FPGA offloads, and zero-copy Python bindings).

### Core Ecosystem

| Repository | Domain | Architecture & Stack |
| :--- | :--- | :--- |
| **[`isme`](https://github.com/quantkernel/isme)** | **Exchange Connectivity & Market Data** | Unified async international stock market engine, normalized L1/L2/L3 schemas, and resilient transport (`Python` / `HTTPX` / `Pydantic`) |
| **[`trishul`](https://github.com/quantkernel/trishul)** | **Market Microstructure & Execution** | Sub-microsecond L3 limit order book, lock-free matching engine, and hardware-accelerated automated market making (`C++20` / `FPGA`) |
| **[`frtb-kernel`](https://github.com/quantkernel/frtb-kernel)** | **Institutional Market Risk** | High-throughput Expected Shortfall (ES), sensitivities-based method (SBM) aggregation, and default risk charge compute kernels (`C++20` / `nanobind`) |
| **[`qk-bench`](https://github.com/quantkernel/qk-bench)** | **Hardware & Latency Telemetry** | Reproducible P50 / P99 / P99.9 tick-to-trade latency histograms, cache-miss profiling, and SIMD throughput benchmarks (`C++` / `Linux perf`) |

### Engineering Axioms

* **Deterministic Hot Paths:** Zero dynamic heap allocations, lock-free ring buffers, and cache-line-aligned (`alignas(64)`) data structures on critical execution paths.
* **Zero-Copy Language Interop:** Core numerical and event-loop kernels implemented in C++20/23, exposed to Python research pipelines via `nanobind` and the Apache Arrow C Data / PyCapsule interface.
* **Mathematical Rigor:** Exact decimal/fixed-point tick arithmetic for order book state transitions ($c\grave{a}dl\grave{a}g$ lattice accuracy) paired with SIMD-vectorized floating-point kernels for PDE and Monte Carlo pricing.
* **Institutional Licensing:** All libraries are distributed under the **Apache-2.0 License** with explicit patent grants for frictionless adoption across proprietary trading desks and enterprise risk systems.

### Namespace & Packaging Standards

* **C++ Namespace:** `namespace qk::`
* **Python Ecosystem:** `pip install quantkernel` (`import quantkernel as qk`)
* **Citations:** Every flagship repository includes a machine-readable `CITATION.cff` specification for SSRN, arXiv, and academic referencing.
