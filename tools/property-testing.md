# Property-based testing

Generate inputs to falsify invariants/round-trips.

**Reach for this when:** pure-ish functions + a test runner.

_14 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [Hypothesis](https://github.com/HypothesisWorks/hypothesis) | The de-facto property-based testing library for Python. You declare the shape of valid... | Trigger on any Python project with pytest/unittest where you want to find input-handling bugs:... | `pip install hypothesis` | `MPL-2.0` |
| [fast-check](https://github.com/dubzzz/fast-check) | Property-based testing framework for JavaScript/TypeScript written in TypeScript, with... | Trigger on any JS/TS project using Jest/Vitest/Mocha to fuzz pure functions, serializers, validators, and... | `npm install --save-dev fast-check` | `MIT` |
| [proptest](https://github.com/proptest-rs/proptest) | Hypothesis-inspired property testing for Rust. Strategies define how values are... | Trigger on Rust crates to fuzz pure functions, parsers, codecs, and data structures for panics, overflow,... | `cargo test` | `Apache-2.0 OR MIT` |
| [QuickCheck (Haskell)](https://github.com/nick8325/quickcheck) | The original property-based testing library: you write properties (functions returning... | Trigger on Haskell projects to verify algebraic laws and invariants (round-trips, monoid/functor laws,... | `see repo` | `BSD-3-Clause` |
| [Hedgehog (Haskell)](https://github.com/hedgehogqa/haskell-hedgehog) | Modern property testing for Haskell where generators carry their own integrated... | Trigger on Haskell projects that want PBT without writing/maintaining shrink instances, especially when... | `see repo` | `BSD-3-Clause` |
| [RapidCheck](https://github.com/emil-e/rapidcheck) | QuickCheck-style property-based testing for C++ (C++11+) with minimal boilerplate,... | Trigger on C/C++ codebases (via a CMake build) to fuzz pure functions, containers, and serialization for UB,... | `see repo` | `BSD-2-Clause` |
| [ScalaCheck](https://github.com/typelevel/scalacheck) | Property-based testing for Scala and Java with generators (Gen) and properties (Prop),... | Trigger on Scala (or JVM/Java) projects to check algebraic laws, serialization round-trips, and... | `see repo` | `BSD-3-Clause` |
| [FsCheck](https://github.com/fscheck/FsCheck) | Property-based / random testing for .NET, usable from F#, C#, and VB. Provides... | Trigger on .NET codebases to fuzz pure methods, parsers, and serializers for edge-case and boundary bugs,... | `dotnet add package FsCheck (and FsCheck.Xunit for attribute-` | `BSD-3-Clause` |
| [gopter](https://github.com/leanovate/gopter) | GOlang Property TestER: brings ScalaCheck/QuickCheck-style property testing to Go, with... | Trigger on Go projects to fuzz pure functions, encoders/decoders, and data structures for panics and... | `go get github.com/leanovate/gopter` | `MIT` |
| [test.check](https://github.com/clojure/test.check) | The official QuickCheck for Clojure (and ClojureScript): generators produce random... | Trigger on Clojure/ClojureScript projects to test invariants of pure functions, spec-conformance, and data... | `see repo` | `EPL-1.0` |
| [StreamData](https://github.com/whatyouhide/stream_data) | Data generation and property-based testing for Elixir. Generators are composable lazy... | Trigger on Elixir projects using ExUnit to fuzz pure functions, parsers, and encoders, verify round-trips... | `see repo` | `Apache-2.0` |
| [Schemathesis](https://github.com/schemathesis/schemathesis) | Property-based API testing built on Hypothesis: it reads an OpenAPI (2.0/3.0/3.1) or... | Trigger when the target is a web service with an OpenAPI/GraphQL schema and you want to find unhandled-input... | `pip install schemathesis` | `MIT` |
| [PropEr](https://github.com/proper-testing/proper) | QuickCheck-inspired property-based testing for Erlang, tightly integrated with Erlang's... | Trigger on Erlang (and, via propcheck, Elixir) systems to test pure functions and especially... | `see repo` | `GPL-3.0` ⚠️ |
| [jqwik](https://github.com/jqwik-team/jqwik) | Property-based testing as a JUnit 5 test engine for the JVM (Java, Kotlin, Groovy), with... | Trigger on JVM projects already on JUnit 5 that want annotation-driven PBT. IMPORTANT for an AI-agent-driven... | `see repo` | `EPL-2.0` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
