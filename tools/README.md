# Tool catalog

209 tools across 16 categories. Machine-readable: [`../catalog/index.json`](../catalog/index.json).

| Category | Tools | What it covers |
|---|---|---|
| [Fuzzing (coverage-guided & binary)](fuzzing.md) | 12 | Mutate inputs to crash native code. |
| [Language-native fuzzing](lang-native-fuzzing.md) | 14 | In-language fuzz harnesses using the project's own toolchain. |
| [Property-based testing](property-testing.md) | 14 | Generate inputs to falsify invariants/round-trips. |
| [Load & stress testing](load-stress.md) | 16 | Drive a service past nominal load for latency cliffs, leaks, capacity limits. |
| [API / spec / contract fuzzing](api-fuzzing.md) | 12 | Fuzz an HTTP/gRPC surface from its spec. |
| [Chaos engineering & fault injection](chaos.md) | 14 | Inject latency, faults, resource pressure. |
| [Mutation testing](mutation-testing.md) | 12 | Mutate code, check the test suite catches it. |
| [Static analysis / SAST / linters](static-analysis.md) | 16 | Find bugs/vulns without running the code. |
| [Sanitizers & dynamic analysis](sanitizers-dynamic.md) | 9 | Runtime checks for UB, UAF, leaks, data races. |
| [Secret scanning & supply-chain](secret-supplychain.md) | 15 | Scan files, git history, and deps for secrets and known vulns. |
| [DAST / web security scanning](dast-websec.md) | 12 | Dynamically probe a running web app (authorized only). |
| [Browser/UI monkey & E2E stress](ui-monkey-e2e.md) | 11 | Random/structured interaction to surface UI crashes. |
| [Database / SQL testing & fuzzing](db-sql-testing.md) | 13 | Generate queries/workloads, check DB logic & consistency. |
| [Concurrency, race & model checking](concurrency-model.md) | 13 | Find races, deadlocks, distributed-systems bugs. |
| [Performance profiling & benchmarking](perf-profiling-bench.md) | 14 | Profile hotspots, track regressions, watch memory growth. |
| [Automated test/input generation & concolic](test-generation.md) | 12 | Auto-generate tests/inputs; explore reachability symbolically. |

⚠️ some tools are copyleft/commercial - install from upstream, never copy their source into your project.
