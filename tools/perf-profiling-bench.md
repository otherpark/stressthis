# Performance profiling & benchmarking

Profile hotspots, track regressions, watch memory growth.

**Reach for this when:** performance matters / benchmarks exist.

_14 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [hyperfine](https://github.com/sharkdp/hyperfine) | Command-line benchmarking tool that runs arbitrary shell commands repeatedly, performs... | When you need black-box wall-clock benchmarking of any CLI invocation (build steps, scripts, binaries,... | `cargo install hyperfine or brew install hyperfine or apt ins` | `MIT OR Apache-2.0` |
| [py-spy](https://github.com/benfred/py-spy) | Sampling profiler for Python programs that reads the target process's memory from... | When a Python service/script is slow, hot-looping, or hung in production and you cannot modify or restart... | `pip install py-spy` | `MIT` |
| [Google Benchmark](https://github.com/google/benchmark) | Microbenchmark support library for C++ (with Python bindings) modeled on GoogleTest. You... | When you need precise, statistically sound microbenchmarks of C/C++ functions or hot inner loops to catch... | `apt install libbenchmark-dev / brew install google-benchmark` | `Apache-2.0` |
| [Criterion.rs](https://github.com/criterion-rs/criterion.rs) | Statistics-driven benchmarking library for Rust. Runs each benchmark many times, applies... | When benchmarking Rust functions/crates and you want automatic regression detection between runs with... | `cargo bench` | `Apache-2.0 OR MIT` |
| [pprof (google/pprof)](https://github.com/google/pprof) | Tool for visualization and analysis of profiling data in the profile.proto format. Reads... | When you have a Go service (or any pprof-format profile) and need to find CPU hotspots, memory allocation... | `go install github.com/google/pprof@latest` | `Apache-2.0` |
| [Valgrind Callgrind](https://github.com/tomhughes/valgrind) | Callgrind is a Valgrind tool that records the call graph and per-function/per-line... | When you need exact, repeatable instruction-level profiling of a native (C/C++/Rust/etc.) binary to find the... | `apt install valgrind / brew install valgrind (Linux primaril` | `GPL-2.0-or-later` ⚠️ |
| [Linux perf (perf_events)](https://github.com/torvalds/linux/tree/master/tools/perf) | The standard Linux system profiler, part of the kernel source tree. Uses hardware... | When profiling any native or JIT workload on Linux and you need low-overhead, whole-system CPU hotspot... | `apt install linux-tools-common linux-tools-$(uname -r) (Linu` | `GPL-2.0-only` ⚠️ |
| [Memray](https://github.com/bloomberg/memray) | Memory profiler for Python by Bloomberg that tracks every allocation in Python code,... | When a Python program (or its C/C++ extensions) leaks memory, has unexpected peak RSS, or allocates... | `pip install memray` | `Apache-2.0` |
| [Scalene](https://github.com/plasma-umass/scalene) | High-precision CPU, GPU, and memory profiler for Python with very low overhead.... | When you need a single tool to pinpoint both CPU and memory hotspots in a Python program at line granularity... | `pip install -U scalene` | `Apache-2.0` |
| [Austin](https://github.com/P403n1x87/austin) | Frame-stack sampling profiler for CPython written in pure C. Reads the interpreter's... | When you want an extremely lightweight, dependency-free statistical profiler for a Python process (including... | `pip install austin-dist` | `GPL-3.0-or-later` ⚠️ |
| [Tracy Profiler](https://github.com/wolfpld/tracy) | Real-time, nanosecond-resolution hybrid frame-and-sampling profiler with remote... | When profiling a frame-based or latency-sensitive C/C++ application (game loop, renderer, audio/realtime... | `see repo` | `BSD-3-Clause` |
| [Airspeed Velocity (asv)](https://github.com/airspeed-velocity/asv) | Benchmarking framework for tracking Python package performance across its git history.... | When maintaining a Python library and you want continuous performance regression tracking across commits... | `pip install asv` | `BSD-3-Clause` |
| [pyperf](https://github.com/psf/pyperf) | PSF-maintained toolkit to write, run, and analyze Python microbenchmarks reliably.... | When you need statistically trustworthy Python microbenchmarks and want to minimize measurement noise (it... | `pip install pyperf` | `MIT` |
| [bpftrace](https://github.com/bpftrace/bpftrace) | High-level tracing language and tool for Linux built on eBPF. Lets you write awk/C-like... | When diagnosing performance or behavior of a running Linux system/process under load and you need custom,... | `apt install bpftrace / dnf install bpftrace (Linux` | `Apache-2.0` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
