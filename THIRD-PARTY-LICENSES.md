# Third-Party Licenses

stressthis is a **pointer catalog**: it bundles no tool source. Every tool below is installed
from its own upstream project under its own license. This repo's MIT `LICENSE` covers only its own
content (the lists/docs). When you install a tool, that tool's license governs your use; tools
marked **copyleft** (GPL/AGPL) must not have their source copied into your project.

_209 tools across 16 categories._

## Fuzzing (coverage-guided & binary) (`fuzzing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| AFL (american fuzzy lop, original) | https://github.com/google/AFL | `Apache-2.0` | no |
| AFL++ | https://github.com/AFLplusplus/AFLplusplus | `AGPL-3.0-or-later` | **yes** |
| Atheris | https://github.com/google/atheris | `Apache-2.0` | no |
| cargo-fuzz | https://github.com/rust-fuzz/cargo-fuzz | `Apache-2.0 OR MIT` | no |
| Fuzzilli | https://github.com/googleprojectzero/fuzzilli | `Apache-2.0` | no |
| FuzzTest (incl. Centipede) | https://github.com/google/fuzztest | `Apache-2.0` | no |
| honggfuzz | https://github.com/google/honggfuzz | `Apache-2.0` | no |
| Jazzer | https://github.com/CodeIntelligenceTesting/jazzer | `Apache-2.0` | no |
| LibAFL | https://github.com/AFLplusplus/LibAFL | `MIT OR Apache-2.0` | no |
| libFuzzer | https://github.com/llvm/llvm-project/tree/main/compiler-rt/lib/fuzzer | `Apache-2.0 WITH LLVM-exception` | no |
| syzkaller | https://github.com/google/syzkaller | `Apache-2.0` | no |
| WinAFL | https://github.com/googleprojectzero/winafl | `Apache-2.0` | no |

## Language-native fuzzing (`lang-native-fuzzing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| afl.rs (cargo-afl) | https://github.com/rust-fuzz/afl.rs | `Apache-2.0` | no |
| Atheris | https://github.com/google/atheris | `Apache-2.0` | no |
| bolero (cargo-bolero) | https://github.com/camshaft/bolero | `MIT` | no |
| cargo-fuzz | https://github.com/rust-fuzz/cargo-fuzz | `Apache-2.0 OR MIT` | no |
| fast-check | https://github.com/dubzzz/fast-check | `MIT` | no |
| Go native fuzzing (testing.F) | https://github.com/golang/go | `BSD-3-Clause` | no |
| go-118-fuzz-build | https://github.com/AdamKorcz/go-118-fuzz-build | `Apache-2.0` | no |
| go-fuzz | https://github.com/dvyukov/go-fuzz | `Apache-2.0` | no |
| honggfuzz-rs | https://github.com/rust-fuzz/honggfuzz-rs | `Apache-2.0 OR MIT` | no |
| HypoFuzz | https://github.com/Zac-HD/hypofuzz | `LicenseRef-Proprietary` | **yes** |
| Hypothesis | https://github.com/HypothesisWorks/hypothesis | `MPL-2.0` | no |
| Jazzer | https://github.com/CodeIntelligenceTesting/jazzer | `Apache-2.0` | no |
| Jazzer.js | https://github.com/CodeIntelligenceTesting/jazzer.js | `Apache-2.0` | no |
| SharpFuzz | https://github.com/Metalnem/sharpfuzz | `MIT` | no |

## Property-based testing (`property-testing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| fast-check | https://github.com/dubzzz/fast-check | `MIT` | no |
| FsCheck | https://github.com/fscheck/FsCheck | `BSD-3-Clause` | no |
| gopter | https://github.com/leanovate/gopter | `MIT` | no |
| Hedgehog (Haskell) | https://github.com/hedgehogqa/haskell-hedgehog | `BSD-3-Clause` | no |
| Hypothesis | https://github.com/HypothesisWorks/hypothesis | `MPL-2.0` | no |
| jqwik | https://github.com/jqwik-team/jqwik | `EPL-2.0` | **yes** |
| PropEr | https://github.com/proper-testing/proper | `GPL-3.0` | **yes** |
| proptest | https://github.com/proptest-rs/proptest | `Apache-2.0 OR MIT` | no |
| QuickCheck (Haskell) | https://github.com/nick8325/quickcheck | `BSD-3-Clause` | no |
| RapidCheck | https://github.com/emil-e/rapidcheck | `BSD-2-Clause` | no |
| ScalaCheck | https://github.com/typelevel/scalacheck | `BSD-3-Clause` | no |
| Schemathesis | https://github.com/schemathesis/schemathesis | `MIT` | no |
| StreamData | https://github.com/whatyouhide/stream_data | `Apache-2.0` | no |
| test.check | https://github.com/clojure/test.check | `EPL-1.0` | no |

## Load & stress testing (`load-stress`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Apache JMeter | https://github.com/apache/jmeter | `Apache-2.0` | no |
| Artillery | https://github.com/artilleryio/artillery | `MPL-2.0` | no |
| autocannon | https://github.com/mcollina/autocannon | `MIT` | no |
| bombardier | https://github.com/codesenberg/bombardier | `MIT` | no |
| drill | https://github.com/fcsonline/drill | `GPL-3.0` | **yes** |
| Fortio | https://github.com/fortio/fortio | `Apache-2.0` | no |
| Gatling | https://github.com/gatling/gatling | `Apache-2.0` | no |
| ghz | https://github.com/bojand/ghz | `Apache-2.0` | no |
| hey | https://github.com/rakyll/hey | `Apache-2.0` | no |
| k6 | https://github.com/grafana/k6 | `AGPL-3.0` | **yes** |
| Locust | https://github.com/locustio/locust | `MIT` | no |
| oha | https://github.com/hatoo/oha | `MIT` | no |
| Tsung | https://github.com/processone/tsung | `GPL-2.0` | **yes** |
| Vegeta | https://github.com/tsenart/vegeta | `MIT` | no |
| wrk | https://github.com/wg/wrk | `Apache-2.0 (modified)` | no |
| wrk2 | https://github.com/giltene/wrk2 | `Apache-2.0` | no |

## API / spec / contract fuzzing (`api-fuzzing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| APIFuzzer | https://github.com/KissPeter/APIFuzzer | `GPL-3.0` | **yes** |
| CATS | https://github.com/Endava/cats | `Apache-2.0` | no |
| EvoMaster | https://github.com/WebFuzzing/EvoMaster | `LGPL-3.0` | no |
| fuzz-lightyear | https://github.com/Yelp/fuzz-lightyear | `Apache-2.0` | no |
| Keploy | https://github.com/keploy/keploy | `Apache-2.0` | no |
| openapi-fuzzer (matusf) | https://github.com/matusf/openapi-fuzzer | `AGPL-3.0` | **yes** |
| Pact (pact-js) | https://github.com/pact-foundation/pact-js | `MIT` | no |
| RESTest | https://github.com/isa-group/RESTest | `LGPL-3.0` | no |
| RESTler | https://github.com/microsoft/restler-fuzzer | `MIT` | no |
| RestTestGen | https://github.com/SeUniVr/RestTestGen | `Apache-2.0` | no |
| Schemathesis | https://github.com/schemathesis/schemathesis | `MIT` | no |
| Tcases | https://github.com/Cornutum/tcases | `MIT` | no |

## Chaos engineering & fault injection (`chaos`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Chaos Mesh | https://github.com/chaos-mesh/chaos-mesh | `Apache-2.0` | no |
| Chaos Monkey (Netflix) | https://github.com/Netflix/chaosmonkey | `Apache-2.0` | no |
| Chaos Toolkit | https://github.com/chaostoolkit/chaostoolkit | `Apache-2.0` | no |
| Chaosd | https://github.com/chaos-mesh/chaosd | `Apache-2.0` | no |
| chaoskube | https://github.com/linki/chaoskube | `MIT` | no |
| Comcast | https://github.com/tylertreat/comcast | `Apache-2.0` | no |
| Krkn (kraken) | https://github.com/krkn-chaos/krkn | `Apache-2.0` | no |
| kube-monkey | https://github.com/asobti/kube-monkey | `Apache-2.0` | no |
| LitmusChaos | https://github.com/litmuschaos/litmus | `Apache-2.0` | no |
| Muxy | https://github.com/mefellows/muxy | `MIT` | no |
| PowerfulSeal | https://github.com/bloomberg/powerfulseal | `Apache-2.0` | no |
| Pumba | https://github.com/alexei-led/pumba | `Apache-2.0` | no |
| stress-ng | https://github.com/ColinIanKing/stress-ng | `GPL-2.0` | **yes** |
| Toxiproxy | https://github.com/Shopify/toxiproxy | `MIT` | no |

## Mutation testing (`mutation-testing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| cargo-mutants | https://github.com/sourcefrog/cargo-mutants | `MIT` | no |
| cosmic-ray | https://github.com/sixty-north/cosmic-ray | `MIT` | no |
| go-mutesting (avito-tech fork) | https://github.com/avito-tech/go-mutesting | `MIT` | no |
| gremlins | https://github.com/go-gremlins/gremlins | `Apache-2.0` | no |
| Infection | https://github.com/infection/infection | `BSD-3-Clause` | no |
| mutant | https://github.com/mbj/mutant | `NOASSERTION` | **yes** |
| mutmut | https://github.com/boxed/mutmut | `BSD-3-Clause` | no |
| MutPy | https://github.com/mutpy/mutpy | `Apache-2.0` | no |
| PIT (pitest) | https://github.com/hcoles/pitest | `Apache-2.0` | no |
| Stryker.NET | https://github.com/stryker-mutator/stryker-net | `Apache-2.0` | no |
| Stryker4s | https://github.com/stryker-mutator/stryker4s | `Apache-2.0` | no |
| StrykerJS | https://github.com/stryker-mutator/stryker-js | `Apache-2.0` | no |

## Static analysis / SAST / linters (`static-analysis`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Bandit | https://github.com/PyCQA/bandit | `Apache-2.0` | no |
| clang-tidy | https://github.com/llvm/llvm-project | `Apache-2.0 WITH LLVM-exception` | no |
| clippy | https://github.com/rust-lang/rust-clippy | `MIT OR Apache-2.0` | no |
| CodeChecker | https://github.com/Ericsson/codechecker | `Apache-2.0 WITH LLVM-exception` | no |
| CodeQL CLI | https://github.com/github/codeql-cli-binaries | `GitHub CodeQL Terms & Conditions (proprietary)` | **yes** |
| cppcheck | https://github.com/danmar/cppcheck | `GPL-3.0` | **yes** |
| Error Prone | https://github.com/google/error-prone | `Apache-2.0` | no |
| ESLint | https://github.com/eslint/eslint | `MIT` | no |
| golangci-lint | https://github.com/golangci/golangci-lint | `GPL-3.0` | **yes** |
| gosec | https://github.com/securego/gosec | `Apache-2.0` | no |
| Infer | https://github.com/facebook/infer | `MIT` | no |
| ruff | https://github.com/astral-sh/ruff | `MIT` | no |
| Semgrep | https://github.com/semgrep/semgrep | `LGPL-2.1` | no |
| shellcheck | https://github.com/koalaman/shellcheck | `GPL-3.0` | **yes** |
| SpotBugs | https://github.com/spotbugs/spotbugs | `LGPL-2.1` | no |
| staticcheck | https://github.com/dominikh/go-tools | `MIT` | no |

## Sanitizers & dynamic analysis (`sanitizers-dynamic`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Dr. Memory | https://github.com/DynamoRIO/drmemory | `LGPL-2.1-only` | no |
| DynamoRIO | https://github.com/DynamoRIO/dynamorio | `BSD-3-Clause` | no |
| GCC libsanitizer (gcc -fsanitize=...) | https://github.com/gcc-mirror/gcc | `GPL-3.0-or-later WITH GCC-exception-3.1` | **yes** |
| gperftools (heap profiler / heap checker) | https://github.com/gperftools/gperftools | `BSD-3-Clause` | no |
| heaptrack | https://github.com/KDE/heaptrack | `LGPL-2.1-or-later` | no |
| LLVM compiler-rt sanitizers (AddressSanitizer / UndefinedBehaviorSanitizer / ThreadSanitizer / MemorySanitizer / LeakSanitizer) | https://github.com/llvm/llvm-project | `Apache-2.0 WITH LLVM-exception` | no |
| Memray | https://github.com/bloomberg/memray | `Apache-2.0` | no |
| rr (record & replay debugger) | https://github.com/rr-debugger/rr | `MIT` | no |
| Valgrind (Memcheck / Helgrind / DRD / Massif / DHAT / Cachegrind / Callgrind) | https://sourceware.org/git/valgrind.git | `GPL-2.0-or-later` | **yes** |

## Secret scanning & supply-chain (`secret-supplychain`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| cargo-audit | https://github.com/rustsec/rustsec | `Apache-2.0 OR MIT` | no |
| dependency-check | https://github.com/dependency-check/DependencyCheck | `Apache-2.0` | no |
| detect-secrets | https://github.com/Yelp/detect-secrets | `Apache-2.0` | no |
| ggshield | https://github.com/GitGuardian/ggshield | `MIT` | no |
| gitleaks | https://github.com/gitleaks/gitleaks | `MIT` | no |
| grype | https://github.com/anchore/grype | `Apache-2.0` | no |
| kingfisher | https://github.com/mongodb/kingfisher | `Apache-2.0` | no |
| opengrep | https://github.com/opengrep/opengrep | `LGPL-2.1` | no |
| osv-scanner | https://github.com/google/osv-scanner | `Apache-2.0` | no |
| pip-audit | https://github.com/pypa/pip-audit | `Apache-2.0` | no |
| semgrep (OSS / Community Edition) | https://github.com/semgrep/semgrep | `LGPL-2.1` | no |
| syft | https://github.com/anchore/syft | `Apache-2.0` | no |
| titus | https://github.com/praetorian-inc/titus | `Apache-2.0` | no |
| trivy | https://github.com/aquasecurity/trivy | `Apache-2.0` | no |
| trufflehog | https://github.com/trufflesecurity/trufflehog | `AGPL-3.0` | **yes** |

## DAST / web security scanning (`dast-websec`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| commix | https://github.com/commixproject/commix | `GPL-3.0-or-later` | **yes** |
| dalfox | https://github.com/hahwul/dalfox | `MIT` | no |
| feroxbuster | https://github.com/epi052/feroxbuster | `MIT` | no |
| ffuf | https://github.com/ffuf/ffuf | `MIT` | no |
| katana | https://github.com/projectdiscovery/katana | `MIT` | no |
| Nikto | https://github.com/sullo/nikto | `GPL-3.0-only` | **yes** |
| Nuclei | https://github.com/projectdiscovery/nuclei | `MIT` | no |
| OWASP ZAP (Zed Attack Proxy) | https://github.com/zaproxy/zaproxy | `Apache-2.0` | no |
| sqlmap | https://github.com/sqlmapproject/sqlmap | `GPL-2.0-or-later` | **yes** |
| testssl.sh | https://github.com/drwetter/testssl.sh | `GPL-2.0-only` | **yes** |
| Wapiti | https://github.com/wapiti-scanner/wapiti | `GPL-2.0-only` | **yes** |
| XSStrike | https://github.com/s0md3v/XSStrike | `GPL-3.0-only` | **yes** |

## Browser/UI monkey & E2E stress (`ui-monkey-e2e`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Android UI/Application Exerciser Monkey | https://android.googlesource.com/platform/development/+/master/cmds/monkey | `Apache-2.0` | no |
| Appium | https://github.com/appium/appium | `Apache-2.0` | no |
| Cypress | https://github.com/cypress-io/cypress | `MIT` | no |
| Detox | https://github.com/wix/Detox | `MIT` | no |
| fast-check | https://github.com/dubzzz/fast-check | `MIT` | no |
| Fastbot_Android | https://github.com/bytedance/Fastbot_Android | `LicenseRef-Fastbot-Revised-License` | **yes** |
| gremlins.js | https://github.com/marmelab/gremlins.js | `MIT` | no |
| Playwright | https://github.com/microsoft/playwright | `Apache-2.0` | no |
| Puppeteer | https://github.com/puppeteer/puppeteer | `Apache-2.0` | no |
| Selenium (WebDriver) | https://github.com/SeleniumHQ/selenium | `Apache-2.0` | no |
| WebdriverIO | https://github.com/webdriverio/webdriverio | `MIT` | no |

## Database / SQL testing & fuzzing (`db-sql-testing`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Chaos Mesh | https://github.com/chaos-mesh/chaos-mesh | `Apache-2.0` | no |
| datafusion sqlfuzz (andygrove/sqlfuzz) | https://github.com/andygrove/sqlfuzz | `Apache-2.0` | no |
| go-randgen | https://github.com/pingcap/go-randgen | `NOASSERTION` | **yes** |
| go-sqlsmith | https://github.com/PingCAP-QE/go-sqlsmith | `Apache-2.0` | no |
| Jepsen | https://github.com/jepsen-io/jepsen | `EPL-1.0` | no |
| MariaDB randgen (RQG / Random Query Generator) | https://github.com/MariaDB/randgen | `GPL-2.0` | **yes** |
| pg_prove (TAP-Parser-SourceHandler-pgTAP) | https://github.com/theory/tap-parser-sourcehandler-pgtap | `Artistic-1.0-Perl OR GPL-1.0-or-later` | no |
| pgTAP | https://github.com/theory/pgtap | `PostgreSQL` | no |
| SQLancer | https://github.com/sqlancer/sqlancer | `MIT` | no |
| sqlsmith | https://github.com/anse1/sqlsmith | `GPL-3.0` | **yes** |
| Squirrel | https://github.com/s3team/Squirrel | `MIT` | no |
| tSQLt | https://github.com/tSQLt-org/tSQLt | `Apache-2.0` | no |
| utPLSQL | https://github.com/utPLSQL/utPLSQL | `Apache-2.0` | no |

## Concurrency, race & model checking (`concurrency-model`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Apalache | https://github.com/apalache-mc/apalache | `Apache-2.0` | no |
| Go race detector (go test -race) | https://github.com/golang/go | `BSD-3-Clause` | no |
| Jepsen | https://github.com/jepsen-io/jepsen | `EPL-1.0` | no |
| Loom | https://github.com/tokio-rs/loom | `MIT` | no |
| madsim | https://github.com/madsim-rs/madsim | `Apache-2.0` | no |
| Maelstrom | https://github.com/jepsen-io/maelstrom | `EPL-1.0` | no |
| Microsoft Coyote | https://github.com/microsoft/coyote | `MIT` | no |
| P (p-org) | https://github.com/p-org/P | `MIT` | no |
| rr (record & replay debugger) | https://github.com/rr-debugger/rr | `MIT` | no |
| Shuttle | https://github.com/awslabs/shuttle | `Apache-2.0` | no |
| ThreadSanitizer (TSan, LLVM/Clang & GCC) | https://github.com/llvm/llvm-project | `Apache-2.0 WITH LLVM-exception` | no |
| TLA+ / TLC model checker | https://github.com/tlaplus/tlaplus | `MIT` | no |
| turmoil | https://github.com/tokio-rs/turmoil | `MIT` | no |

## Performance profiling & benchmarking (`perf-profiling-bench`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| Airspeed Velocity (asv) | https://github.com/airspeed-velocity/asv | `BSD-3-Clause` | no |
| Austin | https://github.com/P403n1x87/austin | `GPL-3.0-or-later` | **yes** |
| bpftrace | https://github.com/bpftrace/bpftrace | `Apache-2.0` | no |
| Criterion.rs | https://github.com/criterion-rs/criterion.rs | `Apache-2.0 OR MIT` | no |
| Google Benchmark | https://github.com/google/benchmark | `Apache-2.0` | no |
| hyperfine | https://github.com/sharkdp/hyperfine | `MIT OR Apache-2.0` | no |
| Linux perf (perf_events) | https://github.com/torvalds/linux/tree/master/tools/perf | `GPL-2.0-only` | **yes** |
| Memray | https://github.com/bloomberg/memray | `Apache-2.0` | no |
| pprof (google/pprof) | https://github.com/google/pprof | `Apache-2.0` | no |
| py-spy | https://github.com/benfred/py-spy | `MIT` | no |
| pyperf | https://github.com/psf/pyperf | `MIT` | no |
| Scalene | https://github.com/plasma-umass/scalene | `Apache-2.0` | no |
| Tracy Profiler | https://github.com/wolfpld/tracy | `BSD-3-Clause` | no |
| Valgrind Callgrind | https://github.com/tomhughes/valgrind | `GPL-2.0-or-later` | **yes** |

## Automated test/input generation & concolic (`test-generation`)

| Tool | Upstream | SPDX | Copyleft |
|---|---|---|---|
| angr | https://github.com/angr/angr | `BSD-2-Clause` | no |
| Atheris | https://github.com/google/atheris | `Apache-2.0` | no |
| CrossHair | https://github.com/pschanely/CrossHair | `MIT` | no |
| EvoMaster | https://github.com/WebFuzzing/EvoMaster | `LGPL-3.0` | no |
| EvoSuite | https://github.com/EvoSuite/evosuite | `LGPL-3.0` | no |
| fast-check | https://github.com/dubzzz/fast-check | `MIT` | no |
| Hypothesis | https://github.com/HypothesisWorks/hypothesis | `MPL-2.0` | no |
| KLEE | https://github.com/klee/klee | `NCSA` | no |
| Manticore | https://github.com/trailofbits/manticore | `AGPL-3.0` | **yes** |
| Pynguin | https://github.com/se2p/pynguin | `MIT` | no |
| Randoop | https://github.com/randoop/randoop | `MIT` | no |
| Schemathesis | https://github.com/schemathesis/schemathesis | `MIT` | no |
