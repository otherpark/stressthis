# AGENTS.md - how to use the stressthis catalog

This is the runbook for any AI agent using stressthis. `CLAUDE.md` only points here.

stressthis is a **catalog of pointers** to open-source stress-testing / bug-finding tools. It
contains no tool source and nothing to install. Your job: read the catalog, choose tools that
fit the target project, **install them yourself from each tool's upstream repo**, run them, and
report verified bugs.

---

## 1. Authorization check (do this first, every time)

These tools include fuzzers, web scanners, and load generators. Pointed at a system you do not
own or are not authorized to test, they can be **illegal** (US CFAA, UK Computer Misuse Act,
equivalents elsewhere) and can violate cloud/SaaS terms.

Before you look up, install, or run anything:

1. Confirm the user **owns** the target, or holds **explicit, written authorization** to test it.
2. Agree the **scope** - which hosts/endpoints, how hard, and when.
3. Never point a tool at a third-party host, a production system, or anything outside that scope.
   Network-touching categories (load-stress, dast-websec, api-fuzzing, chaos) default to
   **localhost / a disposable instance the user controls**.
4. If scope is unclear, or you realize you're hitting something out of scope, **stop and ask.**

No authorization, no run. There is no implicit consent.

## 2. Read the catalog (in this order)

1. **[`catalog/index.json`](catalog/index.json)** - the machine-readable index. One entry per
   tool with: `summary` (what it does), `when_to_use`, `upstream` (the repo to install from),
   `install` (a hint), `usage` (how to run it), `license`, `copyleft`, `languages`,
   `bug_classes`, `popularity`. **Select tools from here.**
2. **[`tools/<category>.md`](tools/)** - the same list as browsable per-category tables, if you
   want category context. Each row links to the tool's upstream repo.

## 3. Pick the right tools

Fingerprint the target first (read-only): languages (from manifests like `package.json`,
`go.mod`, `Cargo.toml`, `pyproject.toml`, `pom.xml`, `CMakeLists.txt`), whether it exposes a
network service, whether there's an API spec (`openapi.yaml`/`*.proto`), concurrency
primitives, and how mature the tests are. Then match to categories:

- **Always useful:** `static-analysis`, `secret-supplychain` (language-agnostic).
- **Native code / parsers:** `fuzzing`, `lang-native-fuzzing`, `sanitizers-dynamic`.
- **Has tests:** `mutation-testing`, `property-testing`.
- **Network service:** `load-stress`, `api-fuzzing`, `chaos`, `dast-websec` (authorized only).
- **Concurrency / DB / UI present:** `concurrency-model`, `db-sql-testing`, `ui-monkey-e2e`.

Filter `index.json` by `languages`, `bug_classes`, and `popularity`. Prefer a **minimal,
relevant** set and explain your choices to the user. Don't run a Go race detector on a Python
repo.

## 4. Install each tool from upstream

For each chosen tool, open its `upstream` repo and install/clone it following **that project's**
instructions (the `install` and `usage` fields are quick hints, not a substitute for the repo's
own docs). You are pulling tools from their source projects - stressthis does not provide them.

Honor licenses: tools flagged `copyleft: true` (GPL/AGPL) or commercial are installed as
external tools - **never copy their source into the user's project**. See
[`THIRD-PARTY-LICENSES.md`](THIRD-PARTY-LICENSES.md).

## 5. Run a multi-agent bug hunt

To find as many real bugs as possible, parallelize and verify:

1. **Triage** (you, once): produce the target fingerprint and the shortlist of categories/tools.
2. **Fan out**: run each category's tools in parallel - ideally one subordinate agent (or
   thread / worktree) per category so builds and instrumentation don't collide. Run everything
   **in a sandbox** (e.g. a container with no network by default, a non-root user, and resource
   limits) - fuzzers execute arbitrary inputs and can write files, open sockets, or exhaust
   memory/disk. Each tool's findings should carry a **deterministic reproducer** (an input file,
   a command, or a failing test); a finding with no repro is a lead, not a bug.
3. **Dedupe**: multiple tools often report the same defect. Collapse duplicates by crash
   signature or `file:line`; a bug found by several tools is higher-confidence.
4. **Verify adversarially**: have a **different** agent, starting from a clean checkout,
   re-run each reproducer and read the surrounding code to confirm the bug is real and reachable
   (not a harness artifact or intended behavior). Only confirmed findings go in the report.
5. **Loop** the stochastic tools (fuzzing, property, concurrency, api-fuzzing): feed crashes
   forward as new seeds and turn confirmed bugs into regression tests; stop when no new confirmed
   findings appear for a couple of rounds, or the budget is spent. Deterministic tools (static,
   secrets) run once.

This is where multiple agents / ultracode / parallel threads pay off: independent agents per
category and per verification, with the orchestrator owning the plan and the final report.

## 6. Report

Produce one report of **confirmed** findings, ranked by severity (memory-safety / data-race /
secret-leak / auth-bypass first; test-gaps and lint nits last). For each: which tool(s) found
it, the `file:line`, the reproducer command, the evidence, the suspected root cause, and a fix
direction. Note which categories ran vs. were skipped and why, and keep a short list of rejected
(false-positive) findings so they aren't re-reported next time.

## 7. Adding or correcting a tool

See [`CONTRIBUTING.md`](CONTRIBUTING.md): add a row to the right `tools/<category>.md` table, a
matching entry in `catalog/index.json`, and a line in `THIRD-PARTY-LICENSES.md`. Verify the
license against the upstream repo. No build step, no scripts - it's all lists.

Authorization first, always.
