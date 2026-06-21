# Load & stress testing

Drive a service past nominal load for latency cliffs, leaks, capacity limits.

**Reach for this when:** a network service you are authorized to test.

_16 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [k6](https://github.com/grafana/k6) | Modern scriptable load-testing tool. Tests are written as JavaScript/TypeScript that... | When you need code-defined, CI-gatable load tests for an HTTP/gRPC/WebSocket API and want to assert... | `brew install k6 or download release binary` | `AGPL-3.0` ⚠️ |
| [Locust](https://github.com/locustio/locust) | Distributed, scriptable load-testing tool where user behavior is defined in plain Python... | When the target project is Python-centric or the load scenario needs real branching logic / stateful user... | `pip install locust` | `MIT` |
| [Vegeta](https://github.com/tsenart/vegeta) | Constant-request-rate HTTP load tester and Go library with UNIX-pipe composability.... | When you need to pin an exact request rate against an HTTP endpoint (e.g. 'can it hold 2000 req/s for 5... | `brew install vegeta or go install github.com/tsenart/vegeta/` | `MIT` |
| [wrk](https://github.com/wg/wrk) | High-performance multithreaded HTTP benchmarking tool that generates large load from a... | When you need to push maximum sustainable throughput at a single HTTP endpoint from one box to find the... | `brew install wrk` | `Apache-2.0 (modified)` |
| [wrk2](https://github.com/giltene/wrk2) | A fork of wrk by Gil Tene that adds a constant-throughput mode (-R) and corrects for... | When you specifically need trustworthy tail-latency numbers (p99/p99.9) at a fixed request rate and suspect... | `clone + build from source` | `Apache-2.0` |
| [hey](https://github.com/rakyll/hey) | Tiny ApacheBench (ab) replacement that sends a configurable number of concurrent HTTP... | When you want a zero-config one-liner smoke/load check of a single HTTP endpoint (quick 'is it fast enough /... | `brew install hey or go install github.com/rakyll/hey@latest` | `Apache-2.0` |
| [oha](https://github.com/hatoo/oha) | hey-inspired HTTP load generator written in Rust with a real-time terminal UI showing... | When you want a modern, fast single-endpoint load test with live visual feedback during the run, or need... | `cargo install oha or brew install oha` | `MIT` |
| [bombardier](https://github.com/codesenberg/bombardier) | Fast HTTP(S) benchmarking tool built on fasthttp (with net/http fallback for HTTP/2).... | When you want a high-throughput, dependency-free single-binary load test of an HTTP endpoint and prefer Go... | `go install github.com/codesenberg/bombardier@latest or downl` | `MIT` |
| [autocannon](https://github.com/mcollina/autocannon) | Fast HTTP/1.1 benchmarking tool for Node, inspired by wrk/wrk2, with HTTP pipelining and... | When the target project is a Node.js/JavaScript service and you want benchmarking that lives in the same... | `npm i -g autocannon` | `MIT` |
| [Artillery](https://github.com/artilleryio/artillery) | Load and functional testing platform driven by YAML scenarios (with JS hooks). Supports... | When you need scenario-based load testing of multi-step user journeys (auth -> API calls -> assertions)... | `npm install -g artillery` | `MPL-2.0` |
| [Gatling](https://github.com/gatling/gatling) | High-performance load-testing framework with a code-based DSL (Scala/Java/Kotlin/JS).... | When the target is a JVM project or you need expressive, maintainable scenario code with built-in assertions... | `see repo` | `Apache-2.0` |
| [Apache JMeter](https://github.com/apache/jmeter) | Mature, GUI-and-CLI load-testing application supporting many protocols: HTTP/HTTPS,... | When you must load-test protocols beyond HTTP (JDBC databases, JMS queues, LDAP, FTP) or need an... | `brew install jmeter (needs Java 17+` | `Apache-2.0` |
| [ghz](https://github.com/bojand/ghz) | Simple gRPC benchmarking and load-testing tool (and Go library). Loads proto files or... | When the target project exposes a gRPC API (not plain HTTP) and you need to measure RPC latency percentiles,... | `brew install ghz or go install github.com/bojand/ghz/cmd/ghz` | `Apache-2.0` |
| [Fortio](https://github.com/fortio/fortio) | Load-testing tool and Go library (originally Istio's) that runs at a specified QPS and... | When you need precise fixed-QPS load testing of HTTP or gRPC with accurate histogram percentiles, ideally... | `brew install fortio or go install fortio.org/fortio@latest` | `Apache-2.0` |
| [drill](https://github.com/fcsonline/drill) | Lightweight HTTP load-testing tool written in Rust where benchmarks are described in... | When you want a small, fast, declarative (YAML) load test for an HTTP API with chained requests and... | `cargo install drill or download a release binary` | `GPL-3.0` ⚠️ |
| [Tsung](https://github.com/processone/tsung) | Distributed, high-concurrency load-testing framework built on Erlang's lightweight... | When you need to simulate very large numbers of concurrent users across multiple machines, especially for... | `apt-get install tsung / brew install tsung` | `GPL-2.0` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
