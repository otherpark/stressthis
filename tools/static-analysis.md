# Static analysis / SAST / linters

Find bugs/vulns without running the code.

**Reach for this when:** always - a linter exists for nearly every language.

_16 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [Semgrep](https://github.com/semgrep/semgrep) | Pattern-based semantic static analysis (semantic grep) across 30+ languages. Finds bugs,... | Polyglot repo or any single-language project where you want fast custom or registry-driven taint/SAST rules... | `pip install semgrep` | `LGPL-2.1` |
| [CodeQL CLI](https://github.com/github/codeql-cli-binaries) | Semantic code analysis engine that compiles code into a relational database and runs QL... | Open-source or academic codebase needing deep interprocedural dataflow/taint analysis beyond pattern... | `see repo` | `GitHub CodeQL Terms & Conditions (proprietary)` ⚠️ |
| [ruff](https://github.com/astral-sh/ruff) | Extremely fast Python linter and formatter (Rust) implementing 900+ rules that... | Any Python project where you want fast lint coverage for code-quality bugs, unused imports/vars, undefined... | `pip install ruff` | `MIT` |
| [Bandit](https://github.com/PyCQA/bandit) | Security linter for Python that builds an AST and runs security plugins to flag common... | Python codebase where you specifically want security-focused findings (CWE-style) rather than style; good as... | `pip install bandit` | `Apache-2.0` |
| [gosec](https://github.com/securego/gosec) | Go security checker that scans the Go AST and SSA for security problems: injection, weak... | Go project where you want dedicated security/SAST findings (the security counterpart to general Go linters). | `go install github.com/securego/gosec/v2/cmd/gosec@latest` | `Apache-2.0` |
| [staticcheck](https://github.com/dominikh/go-tools) | State-of-the-art Go linter that finds correctness bugs, performance issues, dead code,... | Go project where you want high-signal correctness/bug detection (nil derefs, impossible type assertions,... | `go install honnef.co/go/tools/cmd/staticcheck@latest` | `MIT` |
| [clippy](https://github.com/rust-lang/rust-clippy) | Official Rust linter with 800+ lints catching correctness bugs, suspicious code,... | Any Rust/Cargo project to catch correctness bugs (e.g. incorrect comparisons, swapped args, redundant... | `cargo clippy --all-targets (add --fix to autofix` | `MIT OR Apache-2.0` |
| [cppcheck](https://github.com/danmar/cppcheck) | Static analyzer for C/C++ focused on detecting bugs with low false positives:... | C/C++ project (especially without a compile_commands.json) where you want a standalone bug-finder for memory... | `brew install cppcheck` | `GPL-3.0` ⚠️ |
| [clang-tidy](https://github.com/llvm/llvm-project) | Clang-based C/C++ linter and static analyzer with hundreds of checks (bugprone-*,... | C/C++ project that has (or can generate) compile_commands.json and you want compiler-accurate bug detection... | `apt-get install clang-tidy` | `Apache-2.0 WITH LLVM-exception` |
| [Infer](https://github.com/facebook/infer) | Meta's interprocedural static analyzer using separation logic and abstract... | Java, C, C++, or Objective-C project where you want deep interprocedural bug detection (null-pointer, leaks,... | `brew install infer` | `MIT` |
| [Error Prone](https://github.com/google/error-prone) | Google's compile-time static analysis for Java that hooks into javac to catch common... | Java project built with Bazel/Maven/Gradle where you want bug detection wired into the compile step (catches... | `see repo` | `Apache-2.0` |
| [shellcheck](https://github.com/koalaman/shellcheck) | Static analysis for bash/sh shell scripts: flags quoting bugs (unquoted $var... | Any project with shell scripts (.sh, CI scripts, Dockerfiles' RUN lines) to catch quoting/portability bugs... | `brew install shellcheck` | `GPL-3.0` ⚠️ |
| [golangci-lint](https://github.com/golangci/golangci-lint) | Fast parallel meta-runner that bundles 100+ Go linters (incl. staticcheck, govet, gosec,... | Go project where you want one command to run a broad battery of correctness/bug/style linters in CI. Run as... | `brew install golangci-lint` | `GPL-3.0` ⚠️ |
| [ESLint](https://github.com/eslint/eslint) | Pluggable linter for JavaScript/TypeScript that builds an AST and reports problematic... | Any JS/TS project where you want to catch correctness bugs (undefined vars, unhandled promises, accidental... | `npm init @eslint/config@latest` | `MIT` |
| [SpotBugs](https://github.com/spotbugs/spotbugs) | Successor to FindBugs; analyzes Java bytecode to detect bug patterns: null-pointer... | Compiled Java project where you want bytecode-level bug detection; pair with the find-sec-bugs plugin for... | `see repo` | `LGPL-2.1` |
| [CodeChecker](https://github.com/Ericsson/codechecker) | Analyzer driver, defect database, and web viewer built on LLVM/Clang. Replaces... | C/C++ (or mixed) project where you want to run multiple C/C++ analyzers together with cross-translation-unit... | `pip3 install codechecker` | `Apache-2.0 WITH LLVM-exception` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
