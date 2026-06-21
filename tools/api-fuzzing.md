# API / spec / contract fuzzing

Fuzz an HTTP/gRPC surface from its spec.

**Reach for this when:** an OpenAPI/gRPC spec or an in-scope HTTP surface.

_12 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [Schemathesis](https://github.com/schemathesis/schemathesis) | Property-based API testing engine (built on Hypothesis) that reads an OpenAPI or GraphQL... | You have a service with an OpenAPI/GraphQL schema and want to find unhandled-input crashes, undocumented... | `uv pip install schemathesis` | `MIT` |
| [RESTler](https://github.com/microsoft/restler-fuzzer) | Microsoft Research's stateful REST API fuzzer. Analyzes an OpenAPI/Swagger spec, infers... | You have a stateful cloud REST service (resources created/referenced/deleted across calls) and want to find... | `see repo` | `MIT` |
| [CATS](https://github.com/Endava/cats) | REST API fuzzer and negative-testing tool with 100+ built-in fuzzers covering boundary... | You have an OpenAPI 3 spec and want broad automated negative/boundary coverage and contract-conformance... | `brew tap endava/tap` | `Apache-2.0` |
| [Pact (pact-js)](https://github.com/pact-foundation/pact-js) | Consumer-driven contract testing framework. The consumer writes unit tests against a... | You have a microservice architecture where one service consumes another's HTTP API (or async messages) and... | `npm install --save-dev @pact-foundation/pact` | `MIT` |
| [EvoMaster](https://github.com/WebFuzzing/EvoMaster) | AI-driven (evolutionary search + dynamic program analysis) system-level test generator... | You want the highest code-coverage/defect-finding fuzzing and can either point it at a schema (black-box) or... | `pip install evomaster` | `LGPL-3.0` |
| [Tcases](https://github.com/Cornutum/tcases) | Model-based test-case generator. Its tcases-openapi module derives a system input model... | You want systematic, combinatorial input-space coverage of each API operation (valid + invalid value... | `see repo` | `MIT` |
| [fuzz-lightyear](https://github.com/Yelp/fuzz-lightyear) | Yelp's pytest-inspired DAST framework for stateful Swagger fuzzing in microservice... | You have a Swagger/OpenAPI-described microservice ecosystem and want to hunt authorization bugs, especially... | `pip install fuzz-lightyear` | `Apache-2.0` |
| [RestTestGen](https://github.com/SeUniVr/RestTestGen) | Research framework for automated black-box testing of RESTful APIs. Builds an... | You want dependency-aware black-box sequence testing of a REST API (nominal + error scenarios) from just an... | `docker run --rm --network host -v ./apis/:/app/apis/ rtg` | `Apache-2.0` |
| [RESTest](https://github.com/isa-group/RESTest) | Model-based black-box testing framework for RESTful web APIs. Derives test cases... | Your OpenAPI API has inter-parameter dependencies (e.g. 'param A required only if B present') and you want a... | `see repo` | `LGPL-3.0` |
| [Keploy](https://github.com/keploy/keploy) | Open-source record-and-replay testing platform. Captures real API traffic (HTTP, plus... | You have a running service and want regression and de-facto contract tests generated from real traffic (no... | `see repo` | `Apache-2.0` |
| [openapi-fuzzer (matusf)](https://github.com/matusf/openapi-fuzzer) | Lightweight black-box fuzzer in Rust that takes an OpenAPI v3 spec (YAML/JSON) plus a... | You want a fast, dependency-free single-binary fuzzer to quickly shake out crash bugs from an OpenAPI 3... | `cargo install openapi-fuzzer` | `AGPL-3.0` ⚠️ |
| [APIFuzzer](https://github.com/KissPeter/APIFuzzer) | No-code fuzzer that reads an OpenAPI/Swagger (v2/v3) definition, mutates... | You want a simple CI-friendly fuzzer that turns a Swagger/OpenAPI spec into JUnit-reportable negative tests... | `pip3 install APIFuzzer` | `GPL-3.0` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
