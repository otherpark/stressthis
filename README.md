<h1 align="center">stressthis</h1>

<p align="center">
  <b>A pointer catalog of open-source stress-testing & bug-finding tools, for AI agents to use.</b><br>
  Point your coding agent at this repo. It looks up the right tools for <i>your</i> project,
  finds their upstream repos, and installs/clones what it needs to hunt for bugs -
  fuzzing, property testing, load & chaos, static analysis, sanitizers, secret scanning, and more.
</p>

---

> ### ⚠️ Authorized use only
> Only run these tools against software and systems **you own** or are **explicitly authorized to
> test**. Unauthorized fuzzing, scanning, or load-testing of third-party or production systems can
> be illegal (e.g. the US CFAA, the UK Computer Misuse Act) and violate cloud/SaaS terms. This
> project is for finding bugs in **your own** code. You are responsible for where you point these
> tools. See [`AGENTS.md`](AGENTS.md) for the authorization checklist an agent must follow.

---

## What this is

stressthis is a **catalog of pointers**, not a framework and not a bundle of tools. It holds no
tool source code and nothing to install. It is:

- **A machine-readable index** - [`catalog/index.json`](catalog/index.json): **209 tools across
  16 categories**, each with what it does, when to use it, its upstream repo, an install hint,
  its license, target languages, and bug classes. This is what an agent reads to choose tools.
- **Per-category tables** - [`tools/`](tools/): the same list, browsable, one page per category
  with a link to each tool's upstream repo.
- **An agent runbook** - [`AGENTS.md`](AGENTS.md) (with a one-line [`CLAUDE.md`](CLAUDE.md)
  pointer): how to pick tools, install them from upstream, and run a multi-agent bug hunt.

The agent **clones/installs each tool from its own upstream project**. stressthis never copies a
tool's source. The repo's own [MIT license](LICENSE) covers only these lists and docs.

## How an agent uses it

1. Read [`AGENTS.md`](AGENTS.md) - start with the authorization check.
2. Confirm the user owns / is authorized to test the target, and agree on scope.
3. Read [`catalog/index.json`](catalog/index.json); fingerprint the target (language, build,
   service, tests); pick a minimal relevant set of tools.
4. For each chosen tool, go to its `upstream` repo and install/clone it per that project's docs.
5. Run the tools (in a sandbox), then dedupe and **verify** findings before reporting.

## The 16 categories

| Category | What it covers |
|---|---|
| [Fuzzing](tools/fuzzing.md) | Coverage-guided & binary fuzzers (libFuzzer, AFL++, honggfuzz, Atheris, Jazzer) |
| [Language-native fuzzing](tools/lang-native-fuzzing.md) | In-language fuzz harnesses (cargo-fuzz, Go `testing.F`, fast-check) |
| [Property-based testing](tools/property-testing.md) | Falsify invariants with generated inputs (Hypothesis, fast-check, proptest) |
| [Load & stress](tools/load-stress.md) | Latency cliffs, leaks, capacity limits (k6, Locust, Vegeta, wrk, oha) |
| [API / spec fuzzing](tools/api-fuzzing.md) | Spec/contract violations, 5xx, auth gaps (Schemathesis, RESTler, EvoMaster) |
| [Chaos & fault injection](tools/chaos.md) | Failures under injected faults (Toxiproxy, Pumba, Chaos Mesh) |
| [Mutation testing](tools/mutation-testing.md) | Gaps in your test suite (mutmut, StrykerJS, PIT, cargo-mutants) |
| [Static analysis / SAST](tools/static-analysis.md) | Bugs/vulns without running code (Semgrep, ruff, clippy, gosec, CodeQL) |
| [Sanitizers & dynamic](tools/sanitizers-dynamic.md) | UB, UAF, leaks, races at runtime (ASan/UBSan/TSan, Valgrind, rr) |
| [Secrets & supply-chain](tools/secret-supplychain.md) | Leaked secrets, vulnerable deps (gitleaks, trivy, osv-scanner, pip-audit) |
| [DAST / web security](tools/dast-websec.md) | Web vulns, authorized only (OWASP ZAP, Nuclei, dalfox, ffuf) |
| [UI monkey & E2E](tools/ui-monkey-e2e.md) | UI crashes under random interaction (gremlins.js, Playwright, Android Monkey) |
| [DB / SQL testing](tools/db-sql-testing.md) | DB logic & consistency bugs (SQLancer, pgTAP, Jepsen) |
| [Concurrency & model checking](tools/concurrency-model.md) | Races, deadlocks, distributed bugs (Go `-race`, TSan, Loom, TLA+) |
| [Performance & profiling](tools/perf-profiling-bench.md) | Hotspots, regressions, memory growth (hyperfine, py-spy, Criterion.rs) |
| [Test/input generation](tools/test-generation.md) | Auto-generate tests, reachability (EvoSuite, Pynguin, CrossHair, KLEE) |

Browse the full list in [`tools/`](tools/README.md), or grep [`catalog/index.json`](catalog/index.json).

## Licensing

Every tool is listed by **reference** and stays under **its own license** - see
[`THIRD-PARTY-LICENSES.md`](THIRD-PARTY-LICENSES.md). Tools marked ⚠️ (copyleft: GPL/AGPL, or
commercial) must be installed from upstream and **never** have their source copied into your
project. stressthis's own content is [MIT](LICENSE). Want to add a tool? See
[`CONTRIBUTING.md`](CONTRIBUTING.md).
