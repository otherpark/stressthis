# Secret scanning & supply-chain

Scan files, git history, and deps for secrets and known vulns.

**Reach for this when:** always - language-agnostic.

_15 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [gitleaks](https://github.com/gitleaks/gitleaks) | Regex + entropy based secret scanner for git repos, directories, and stdin. Detects... | Any repo with git history where you suspect committed credentials. Best trigger: gate CI or pre-commit to... | `brew install gitleaks or docker pull zricethezav/gitleaks` | `MIT` |
| [trufflehog](https://github.com/trufflesecurity/trufflehog) | Finds, verifies, and analyzes leaked credentials across git, GitHub/GitLab, filesystems,... | When you need not just detection but confirmation that a found secret is still valid/active (live... | `brew install trufflehog or docker run --rm -v "$PWD:/pwd" tr` | `AGPL-3.0` ⚠️ |
| [trivy](https://github.com/aquasecurity/trivy) | All-in-one scanner: dependency/OS-package vulnerabilities (SCA), IaC/misconfiguration,... | When a project ships a container image or has many language lockfiles and you want one tool to find... | `brew install trivy or docker run aquasec/trivy` | `Apache-2.0` |
| [grype](https://github.com/anchore/grype) | Vulnerability scanner for container images, filesystems, and SBOMs. Matches installed OS... | When you already have (or can generate) an SBOM and want fast CVE matching, or want to scan a built... | `brew install grype` | `Apache-2.0` |
| [osv-scanner](https://github.com/google/osv-scanner) | Google's official frontend to the OSV.dev database. Reads lockfiles and SBOMs across... | When a project has lockfiles (package-lock.json, go.mod, Cargo.lock, poetry.lock, requirements.txt, etc.)... | `go install github.com/google/osv-scanner/v2/cmd/osv-scanner@` | `Apache-2.0` |
| [dependency-check](https://github.com/dependency-check/DependencyCheck) | OWASP software composition analysis tool. Identifies project dependencies and maps them... | Java/Maven/Gradle or .NET projects where you want NVD-backed CVE reporting integrated into the build, or... | `docker pull owasp/dependency-check` | `Apache-2.0` |
| [syft](https://github.com/anchore/syft) | Generates a Software Bill of Materials (SBOM) from container images and filesystems... | When you need a complete dependency inventory/SBOM for a supply-chain audit, or as the first step before... | `brew install syft` | `Apache-2.0` |
| [semgrep (OSS / Community Edition)](https://github.com/semgrep/semgrep) | Static analysis engine with semantic pattern matching across 30+ languages and 2,800+... | When you want secret/credential detection bundled with broader SAST bug-finding (injection, hardcoded keys,... | `pip install semgrep or brew install semgrep` | `LGPL-2.1` |
| [opengrep](https://github.com/opengrep/opengrep) | Fully open-source fork of Semgrep v1.100.0, created after Semgrep moved features behind... | When you want Semgrep-style semantic scanning (including secret/SAST rule packs) entirely offline and... | `see repo` | `LGPL-2.1` |
| [detect-secrets](https://github.com/Yelp/detect-secrets) | Yelp's baseline-oriented secret scanner. Uses regex plugins, keyword, and entropy... | When onboarding secret scanning to an existing repo that already contains accepted/false-positive matches... | `pip install detect-secrets` | `Apache-2.0` |
| [kingfisher](https://github.com/mongodb/kingfisher) | MongoDB's high-performance secret scanner combining Intel Hyperscan SIMD regex with... | When you want very fast scanning over large codebases or deep git history AND active validation that a... | `brew install kingfisher or download a release binary / docke` | `Apache-2.0` |
| [titus](https://github.com/praetorian-inc/titus) | Praetorian's high-performance secret scanner (the active successor in spirit to the... | When you want a permissively-licensed, actively-maintained Go secret scanner with a large curated ruleset... | `see repo` | `Apache-2.0` |
| [ggshield](https://github.com/GitGuardian/ggshield) | GitGuardian's open-source CLI (MIT) that detects 500+ secret types across files, repos,... | When a team already uses (or will sign up for) GitGuardian and wants the broadest hosted secret detector... | `pipx install ggshield or brew install gitguardian/tap/ggshie` | `MIT` |
| [pip-audit](https://github.com/pypa/pip-audit) | Official PyPA tool (by Trail of Bits) that audits Python environments, requirements... | Python projects with requirements.txt / pyproject / an installed venv where you want focused, authoritative... | `pip install pip-audit` | `Apache-2.0` |
| [cargo-audit](https://github.com/rustsec/rustsec) | RustSec's auditing tool that checks a project's Cargo.lock against the RustSec Advisory... | Any Rust/Cargo project with a Cargo.lock where you want to flag dependencies with known security advisories.... | `cargo install cargo-audit` | `Apache-2.0 OR MIT` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
