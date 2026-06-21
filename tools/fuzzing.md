# Fuzzing (coverage-guided & binary)

Mutate inputs to crash native code.

**Reach for this when:** native code, parsers, serializers, any byte-in function.

_12 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [AFL++](https://github.com/AFLplusplus/AFLplusplus) | The de-facto successor to AFL: a coverage-guided, mutation-based fuzzer with... | Use on a C/C++ native target (parser, codec, protocol handler, file format reader) to find memory-safety... | `docker pull aflplusplus/aflplusplus` | `AGPL-3.0-or-later` ⚠️ |
| [libFuzzer](https://github.com/llvm/llvm-project/tree/main/compiler-rt/lib/fuzzer) | In-process, coverage-guided, evolutionary fuzzing engine bundled with LLVM/Clang. You... | Use for a library with small, fast-to-process inputs (format parsers, decompressors, crypto, regex) where... | `bundled with toolchain` | `Apache-2.0 WITH LLVM-exception` |
| [honggfuzz](https://github.com/google/honggfuzz) | Security-oriented, multi-process/multi-threaded coverage-guided fuzzer using software... | Use on a C/C++ target when you want a simple, fast standalone fuzzer (file or persistent-mode) that needs no... | `clone + build from source` | `Apache-2.0` |
| [Fuzzilli](https://github.com/googleprojectzero/fuzzilli) | Coverage-guided fuzzer for dynamic-language interpreters, specialized for JavaScript... | Use when fuzzing a JavaScript engine (V8, SpiderMonkey, JavaScriptCore) or similar JIT/interpreter to find... | `clone + build from source` | `Apache-2.0` |
| [FuzzTest (incl. Centipede)](https://github.com/google/fuzztest) | C++ property-based testing framework that runs FUZZ_TEST(...) cases under... | Use in a C++ project that already uses GoogleTest when you want fuzzing written as unit-style property... | `see repo` | `Apache-2.0` |
| [cargo-fuzz](https://github.com/rust-fuzz/cargo-fuzz) | A cargo subcommand that scaffolds and drives libFuzzer-based coverage-guided fuzzing for... | Use on a Rust crate that parses or processes untrusted input (deserializers, parsers, decoders) to find... | `cargo install cargo-fuzz` | `Apache-2.0 OR MIT` |
| [Atheris](https://github.com/google/atheris) | Coverage-guided, native Python fuzzing engine built on libFuzzer. Instruments Python... | Use on a Python library or CPython C-extension that parses untrusted input to find unhandled exceptions,... | `pip3 install atheris` | `Apache-2.0` |
| [Jazzer](https://github.com/CodeIntelligenceTesting/jazzer) | Coverage-guided, in-process fuzzer for the JVM, built on libFuzzer. Instruments bytecode... | Use on a JVM application/library that handles untrusted input (parsers, deserializers, web handlers) to find... | `see repo` | `Apache-2.0` |
| [LibAFL](https://github.com/AFLplusplus/LibAFL) | A library of reusable fuzzer components in Rust for building custom, high-performance... | Use when off-the-shelf fuzzers don't fit - e.g. a custom target needing bespoke... | `clone + build from source` | `MIT OR Apache-2.0` |
| [WinAFL](https://github.com/googleprojectzero/winafl) | A fork of AFL adapted for fuzzing Windows binaries. Uses persistent-mode harnessing... | Use to fuzz a closed-source Windows application or DLL (file parsers, image/document loaders, services)... | `see repo` | `Apache-2.0` |
| [syzkaller](https://github.com/google/syzkaller) | Unsupervised, coverage-guided kernel fuzzer. Describes syscalls in a declarative... | Use to fuzz an OS kernel or its syscall/driver interface (especially Linux) to find kernel panics, memory... | `clone + build from source` | `Apache-2.0` |
| [AFL (american fuzzy lop, original)](https://github.com/google/AFL) | The original coverage-guided, mutation-based fuzzer by Michał Zalewski that pioneered... | Use only for legacy/reproduction scenarios or when a toolchain pins classic AFL; for any new C/C++ fuzzing... | `clone + build from source` | `Apache-2.0` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
