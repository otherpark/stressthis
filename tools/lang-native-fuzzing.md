# Language-native fuzzing

In-language fuzz harnesses using the project's own toolchain.

**Reach for this when:** a fuzzable entrypoint in a language with a native fuzzer.

_14 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [cargo-fuzz](https://github.com/rust-fuzz/cargo-fuzz) | The de-facto standard Rust fuzzing CLI. Wraps libFuzzer (via libfuzzer-sys) to build,... | A Rust crate (parsers, serializers, decoders, anything taking &[u8] or untrusted input) where you want to... | `cargo install cargo-fuzz` | `Apache-2.0 OR MIT` |
| [afl.rs (cargo-afl)](https://github.com/rust-fuzz/afl.rs) | Runs the AFL++ fuzzer against Rust code. Provides a fuzz!/fuzz_target macro and... | Rust crate where you want AFL++-style fork-server, large parallel campaigns, or dictionaries instead of... | `cargo install cargo-afl` | `Apache-2.0` |
| [honggfuzz-rs](https://github.com/rust-fuzz/honggfuzz-rs) | Wraps Google's honggfuzz security-oriented fuzzer for Rust via a cargo hfuzz subcommand... | Rust crate where you want a third engine alongside cargo-fuzz/afl.rs to diversify mutators and catch... | `cargo install honggfuzz` | `Apache-2.0 OR MIT` |
| [bolero (cargo-bolero)](https://github.com/camshaft/bolero) | A property-testing + fuzzing front-end that lets one harness run under libFuzzer, AFL++,... | Rust crate where you want a single harness portable across multiple fuzzing engines, or want to combine... | `cargo add --dev bolero` | `MIT` |
| [Go native fuzzing (testing.F)](https://github.com/golang/go) | Built into the Go toolchain since Go 1.18. FuzzXxx(f *testing.F) functions with... | Any Go module with functions parsing untrusted input (decoders, validators, network handlers); finds panics,... | `see repo` | `BSD-3-Clause` |
| [go-fuzz](https://github.com/dvyukov/go-fuzz) | The original coverage-guided fuzzer for Go (pre-1.18). Uses a Fuzz(data []byte) int... | Go projects still on the go-fuzz harness style, or where you need its sonar/versifier features or OSS-Fuzz... | `go install github.com/dvyukov/go-fuzz/go-fuzz@latest github.` | `Apache-2.0` |
| [go-118-fuzz-build](https://github.com/AdamKorcz/go-118-fuzz-build) | Converts native Go 1.18 testing.F fuzz harnesses into libFuzzer binaries so they can be... | Go project that already has testing.F fuzz tests and you want to run them under libFuzzer/OSS-Fuzz (e.g.... | `go install github.com/AdamKorcz/go-118-fuzz-build@latest` | `Apache-2.0` |
| [Atheris](https://github.com/google/atheris) | Google's coverage-guided Python fuzzing engine, built on libFuzzer. Instruments Python... | Python package or C extension parsing untrusted input (serializers, decoders, validators); finds uncaught... | `pip3 install atheris` | `Apache-2.0` |
| [Hypothesis](https://github.com/HypothesisWorks/hypothesis) | Property-based testing library that is secretly a structured fuzzer: you describe input... | Python codebase with functions whose properties/invariants you can state (roundtrip, idempotence,... | `pip install hypothesis` | `MPL-2.0` |
| [HypoFuzz](https://github.com/Zac-HD/hypofuzz) | Adaptive coverage-guided fuzzing backend that takes your existing Hypothesis @given... | Python project that already has a Hypothesis test suite and wants to run it as a long-running... | `pip install hypofuzz` | `LicenseRef-Proprietary` ⚠️ |
| [Jazzer](https://github.com/CodeIntelligenceTesting/jazzer) | Coverage-guided, in-process fuzzer for the JVM built on libFuzzer. Instruments bytecode,... | Java/Kotlin/Scala app or library taking untrusted input (parsers, deserializers, web handlers); finds... | `see repo` | `Apache-2.0` |
| [Jazzer.js](https://github.com/CodeIntelligenceTesting/jazzer.js) | Coverage-guided, in-process fuzzer for Node.js, built on libFuzzer. Instruments JS/TS,... | Node.js/TypeScript package parsing or validating untrusted input; finds uncaught exceptions,... | `npm install --save-dev @jazzer.js/core` | `Apache-2.0` |
| [fast-check](https://github.com/dubzzz/fast-check) | Property-based testing / structured fuzzing framework for JS/TS (QuickCheck-style).... | JS/TS codebase with functions whose properties you can express (roundtrip, equivalence, never-throws) or... | `npm install --save-dev fast-check` | `MIT` |
| [SharpFuzz](https://github.com/Metalnem/sharpfuzz) | Coverage-guided fuzzing for .NET that instruments managed IL so it can be driven by... | C#/.NET library parsing untrusted input (file formats, protocols, serializers); finds unhandled exceptions,... | `dotnet tool install --global SharpFuzz.CommandLine` | `MIT` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
