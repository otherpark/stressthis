# Sanitizers & dynamic analysis

Runtime checks for UB, UAF, leaks, data races.

**Reach for this when:** C/C++/Rust/cgo (native code present).

_9 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [LLVM compiler-rt sanitizers (AddressSanitizer / UndefinedBehaviorSanitizer / ThreadSanitizer / MemorySanitizer / LeakSanitizer)](https://github.com/llvm/llvm-project) | The canonical runtime + compiler-instrumentation sanitizers shipped in LLVM/Clang. ASan... | Any C/C++/Objective-C (or Rust/Swift via LLVM) project you can rebuild. Use ASan+UBSan as the default for... | `see repo` | `Apache-2.0 WITH LLVM-exception` |
| [GCC libsanitizer (gcc -fsanitize=...)](https://github.com/gcc-mirror/gcc) | GCC's bundled port of the LLVM sanitizers (ASan, UBSan, TSan, LSan) exposed through the... | C/C++ projects whose toolchain is GCC (common on Linux distros, embedded, kernel-adjacent userspace) where... | `see repo` | `GPL-3.0-or-later WITH GCC-exception-3.1` ⚠️ |
| [Valgrind (Memcheck / Helgrind / DRD / Massif / DHAT / Cachegrind / Callgrind)](https://sourceware.org/git/valgrind.git) | Dynamic binary instrumentation framework that runs an unmodified executable on a... | C/C++ (or any native binary) when you cannot or do not want to rebuild with sanitizers, or need... | `apt-get install valgrind / brew install valgrind` | `GPL-2.0-or-later` ⚠️ |
| [rr (record & replay debugger)](https://github.com/rr-debugger/rr) | Records a deterministic trace of a program's execution (all nondeterministic inputs and... | Linux x86-64/aarch64 native programs with intermittent or heisenbug-style failures (race-dependent crashes,... | `apt-get install rr or from releases` | `MIT` |
| [heaptrack](https://github.com/KDE/heaptrack) | Heap memory profiler for Linux that traces every allocation/deallocation with full stack... | Native C/C++ Linux applications with high memory usage, leaks, or allocation churn you need to attribute to... | `apt-get install heaptrack heaptrack-gui / brew not supported` | `LGPL-2.1-or-later` |
| [Dr. Memory](https://github.com/DynamoRIO/drmemory) | Memory-error detector built on the DynamoRIO dynamic instrumentation engine. On... | C/C++ projects, especially Windows ones (where Valgrind is unavailable), needing memory-error and leak... | `apt-get install drmemory where packaged)` | `LGPL-2.1-only` |
| [Memray](https://github.com/bloomberg/memray) | Memory profiler for Python that tracks allocations in Python code, in C/C++ native... | Python applications or test suites with memory growth, leaks, or surprising peak usage, especially when... | `pip install memray` | `Apache-2.0` |
| [gperftools (heap profiler / heap checker)](https://github.com/gperftools/gperftools) | tcmalloc-based performance toolkit whose heap profiler samples allocation call sites to... | Native C/C++ services (especially long-running servers) where you want continuous low-overhead heap... | `apt-get install google-perftools libgoogle-perftools-dev` | `BSD-3-Clause` |
| [DynamoRIO](https://github.com/DynamoRIO/dynamorio) | Runtime code manipulation / dynamic binary instrumentation platform that runs unmodified... | When you need custom dynamic analysis of a native binary you cannot recompile (coverage collection for... | `see repo` | `BSD-3-Clause` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
