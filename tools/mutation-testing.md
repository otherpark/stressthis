# Mutation testing

Mutate code, check the test suite catches it.

**Reach for this when:** an existing test suite with non-trivial coverage.

_12 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [mutmut](https://github.com/boxed/mutmut) | Mutation testing system for Python with a focus on ease of use. It mutates your source... | Use on a Python project that already has a passing pytest/unittest suite and good line coverage, to find... | `pip install mutmut` | `BSD-3-Clause` |
| [cosmic-ray](https://github.com/sixty-north/cosmic-ray) | Mutation testing tool for Python 3 that makes small changes to source code and runs the... | Use on larger Python codebases where you need configurable, distributable mutation runs (parallel workers,... | `pip install cosmic-ray` | `MIT` |
| [MutPy](https://github.com/mutpy/mutpy) | AST-based mutation testing tool for Python 3 source code. Runs against unittest, applies... | Use as a lightweight, dependency-free alternative for small Python projects using unittest, or when you... | `pip install mutpy` | `Apache-2.0` |
| [StrykerJS](https://github.com/stryker-mutator/stryker-js) | Mutation testing framework for JavaScript and TypeScript. Instruments source with... | Use on a JS/TS project (Node or browser) with an existing unit test suite to find weak assertions and... | `npm install --save-dev @stryker-mutator/core` | `Apache-2.0` |
| [Stryker.NET](https://github.com/stryker-mutator/stryker-net) | Mutation testing for .NET (C#/F#) using a 'mutation switching' technique that compiles... | Use on a .NET solution with xUnit/NUnit/MSTest tests to measure real test effectiveness on C# code. Standard... | `dotnet tool install -g dotnet-stryker` | `Apache-2.0` |
| [Stryker4s](https://github.com/stryker-mutator/stryker4s) | Mutation testing framework for Scala, part of the Stryker family. Uses mutation... | Use on Scala (sbt or Maven) projects with ScalaTest/MUnit/etc. to assess test quality. The primary mutation... | `see repo` | `Apache-2.0` |
| [PIT (pitest)](https://github.com/hcoles/pitest) | State-of-the-art mutation testing system for the JVM. Mutates bytecode and runs... | Use on Java/Kotlin/JVM projects with an existing JUnit/TestNG suite to find weakly-tested logic. The... | `see repo` | `Apache-2.0` |
| [cargo-mutants](https://github.com/sourcefrog/cargo-mutants) | Mutation testing for Rust. Generates mutants by replacing function bodies/return values... | Use on any Rust crate/workspace with non-flaky tests to find functions whose behavior isn't actually... | `cargo install --locked cargo-mutants` | `MIT` |
| [mutant](https://github.com/mbj/mutant) | Mutation testing for Ruby. Mutates arithmetic/logical/bitwise operators, return values,... | Use on Ruby projects with RSpec/Minitest to rigorously verify test coverage quality. Note: source is... | `gem install mutant-rspec` | `NOASSERTION` ⚠️ |
| [gremlins](https://github.com/go-gremlins/gremlins) | Mutation testing tool for Go inspired by PITest. Applies mutators (conditionals,... | Use on small-to-medium Go modules (e.g. microservices, libraries) with a passing `go test` suite to validate... | `go install github.com/go-gremlins/gremlins/cmd/gremlins@late` | `Apache-2.0` |
| [go-mutesting (avito-tech fork)](https://github.com/avito-tech/go-mutesting) | Mutation testing for Go source code (maintained fork of zimmski/go-mutesting). Applies... | Use on Go projects when you want a configurable, scriptable mutation runner or need mutators/behavior not in... | `go install github.com/avito-tech/go-mutesting/cmd/go-mutesti` | `MIT` |
| [Infection](https://github.com/infection/infection) | AST-based mutation testing framework for PHP. Runs the existing test suite... | Use on PHP projects with a PHPUnit or Pest suite to find weakly-tested code; supports incremental runs over... | `see repo` | `BSD-3-Clause` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
