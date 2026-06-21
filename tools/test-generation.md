# Automated test/input generation & concolic

Auto-generate tests/inputs; explore reachability symbolically.

**Reach for this when:** low coverage and you want generated tests/inputs.

_12 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [EvoSuite](https://github.com/EvoSuite/evosuite) | Automatically generates JUnit test suites for Java classes using an... | Trigger when a Java/JVM project (Maven/Gradle) has classes with little or no unit-test coverage and you want... | `see repo` | `LGPL-3.0` |
| [Randoop](https://github.com/randoop/randoop) | Feedback-directed random test generation for Java. Builds sequences of... | Trigger on a Java project where you want fast, no-config generation of JUnit tests that expose API contract... | `see repo` | `MIT` |
| [Pynguin](https://github.com/se2p/pynguin) | Automated unit-test generation for Python. Uses search-based (evolutionary) and random... | Trigger on a typed-ish Python module/package lacking unit tests, when you want auto-generated pytest cases... | `pip install pynguin` | `MIT` |
| [CrossHair](https://github.com/pschanely/CrossHair) | Concolic / symbolic-execution analysis for Python. Repeatedly calls functions with... | Trigger when Python functions have explicit contracts (asserts, type hints, icontract/deal decorators) and... | `pip install crosshair-tool` | `MIT` |
| [Hypothesis](https://github.com/HypothesisWorks/hypothesis) | Property-based testing library for Python. Generates and shrinks randomized inputs... | Trigger when you want to write or auto-derive property/metamorphic tests for Python functions (encode/decode... | `pip install hypothesis` | `MPL-2.0` |
| [fast-check](https://github.com/dubzzz/fast-check) | Property-based testing framework for JavaScript/TypeScript (QuickCheck-style). Generates... | Trigger on a JS/TS codebase (works with Jest/Vitest/Mocha) where you want to fuzz pure functions and find... | `npm install -D fast-check` | `MIT` |
| [Schemathesis](https://github.com/schemathesis/schemathesis) | Property-based API testing tool (built on Hypothesis) that reads an OpenAPI or GraphQL... | Trigger when the target project exposes a REST/GraphQL API with an OpenAPI/GraphQL schema and you want to... | `pip install schemathesis` | `MIT` |
| [EvoMaster](https://github.com/WebFuzzing/EvoMaster) | AI/evolutionary system-level test (fuzz) generator for web APIs. Black-box mode works... | Trigger on a REST/GraphQL/gRPC service (especially JVM/.NET/Node for white-box) where you want... | `pip install evomaster (v6+` | `LGPL-3.0` |
| [KLEE](https://github.com/klee/klee) | Symbolic execution engine built on LLVM. Runs a program on symbolic inputs, explores... | Trigger on C/C++ (or any LLVM-bitcode) code, especially parsers and utility libraries, when you want... | `docker pull klee/klee` | `NCSA` |
| [angr](https://github.com/angr/angr) | Python binary-analysis platform with a symbolic/concolic execution engine (claripy +... | Trigger when you only have a compiled binary (no source) or want to drive execution to a specific dangerous... | `pip install angr` | `BSD-2-Clause` |
| [Atheris](https://github.com/google/atheris) | Coverage-guided native fuzzing engine for Python (and CPython native extensions), built... | Trigger when a Python project parses untrusted/complex input (binary formats, deserialization, decoders) or... | `pip install atheris` | `Apache-2.0` |
| [Manticore](https://github.com/trailofbits/manticore) | Symbolic execution tool (Trail of Bits) for binaries (x86/ARM), Linux ELF, WASM, and EVM... | Trigger when analyzing a binary or an Ethereum/EVM smart contract and you want to symbolically verify... | `pip install manticore` | `AGPL-3.0` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
