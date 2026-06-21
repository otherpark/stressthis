# Concurrency, race & model checking

Find races, deadlocks, distributed-systems bugs.

**Reach for this when:** concurrency primitives present.

_13 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [Go race detector (go test -race)](https://github.com/golang/go) | Built into the Go toolchain. The -race flag instruments every memory access at compile... | Any Go project with goroutines/channels/shared state. Trigger: intermittent test failures, map concurrent... | `see repo` | `BSD-3-Clause` |
| [ThreadSanitizer (TSan, LLVM/Clang & GCC)](https://github.com/llvm/llvm-project) | Compiler instrumentation (-fsanitize=thread) plus a runtime that detects data races and... | C/C++ projects with pthreads/std::thread/atomics. Trigger: heisenbugs, corruption only under load, suspected... | `see repo` | `Apache-2.0 WITH LLVM-exception` |
| [Loom](https://github.com/tokio-rs/loom) | Exhaustive concurrency permutation tester for Rust. Re-runs a test under every... | Rust crates implementing unsafe concurrency primitives (custom Mutex, lock-free queue, Arc-like type,... | `cargo test --release` | `MIT` |
| [Shuttle](https://github.com/awslabs/shuttle) | Randomized concurrency tester for Rust (PCT / random scheduler with probabilistic... | Larger Rust concurrent systems where Loom's exhaustive search blows up (big async/tokio services, complex... | `cargo test` | `Apache-2.0` |
| [Microsoft Coyote](https://github.com/microsoft/coyote) | Systematic concurrency testing for C#/.NET. Rewrites the IL of test+production binaries... | C#/.NET services using async/await Tasks or in-memory actors (e.g. Azure-style microservices). Trigger:... | `dotnet tool install --global Microsoft.Coyote.CLI and add th` | `MIT` |
| [rr (record & replay debugger)](https://github.com/rr-debugger/rr) | Records a Linux process tree's execution to a trace then replays it deterministically,... | Native Linux programs (C/C++/Rust/Go) with a heisenbug that vanishes under a debugger or won't reproduce.... | `apt install rr) or release binary` | `MIT` |
| [Jepsen](https://github.com/jepsen-io/jepsen) | Black-box distributed-systems safety testing framework. Sets up a real cluster,... | Distributed databases, queues, consensus/coordination services (anything claiming linearizability,... | `see repo` | `EPL-1.0` |
| [Maelstrom](https://github.com/jepsen-io/maelstrom) | A Jepsen-backed workbench for toy distributed systems. Your binary speaks a simple... | Prototyping/validating a distributed algorithm (gossip broadcast, CRDT, replicated KV, consensus) in ANY... | `see repo` | `EPL-1.0` |
| [TLA+ / TLC model checker](https://github.com/tlaplus/tlaplus) | TLC is an explicit-state model checker for TLA+ specifications. It exhaustively (BFS)... | Design-level verification of concurrent/distributed protocols (consensus, locking, cache coherence,... | `see repo` | `MIT` |
| [Apalache](https://github.com/apalache-mc/apalache) | Symbolic (SMT-based, via Z3) model checker for TLA+ and Quint. Does bounded model... | TLA+ specs with large state spaces where TLC times out, or when you want to prove an inductive invariant... | `docker pull ghcr.io/apalache-mc/apalache:main` | `Apache-2.0` |
| [P (p-org)](https://github.com/p-org/P) | A state-machine programming language for modeling event-driven distributed systems plus... | Modeling and verifying async/event-driven distributed protocols as communicating state machines (handshakes,... | `dotnet tool install --global P (needs .NET SDK 8` | `MIT` |
| [madsim](https://github.com/madsim-rs/madsim) | Deterministic simulation runtime for async Rust (tokio-like API). Runs an entire... | Rust distributed systems built on async/tokio (used by RisingWave). Trigger: you want... | `cargo test` | `Apache-2.0` |
| [turmoil](https://github.com/tokio-rs/turmoil) | Deterministic network-simulation test harness for tokio. Runs many simulated hosts in a... | tokio-based networked services/clients where you need reproducible tests of retry logic, timeouts,... | `cargo test` | `MIT` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
