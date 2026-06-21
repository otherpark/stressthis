# Database / SQL testing & fuzzing

Generate queries/workloads, check DB logic & consistency.

**Reach for this when:** a database or SQL layer is present.

_13 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [SQLancer](https://github.com/sqlancer/sqlancer) | Automated logic-bug and performance-bug finder for DBMSs. Generates random schemas and... | You maintain or embed a SQL engine / DBMS (or a query layer like DataFusion) and want to find silent... | `clone + build from source` | `MIT` |
| [sqlsmith](https://github.com/anse1/sqlsmith) | Random SQL query generator modeled on Csmith. Reads the live database catalog to... | You run or wrap PostgreSQL, SQLite3, or MonetDB and want to fuzz the executor for crashes, assertion... | `apt-get install build-essential autoconf autoconf-archive li` | `GPL-3.0` ⚠️ |
| [Squirrel](https://github.com/s3team/Squirrel) | Coverage-guided (AFL/AFL++-based) DBMS fuzzer that keeps SQL in a structural... | You build a C/C++ SQL engine and want memory-safety bugs (heap overflows, UAF, asserts) found via... | `clone + build from source` | `MIT` |
| [pgTAP](https://github.com/theory/pgtap) | Unit-testing suite for PostgreSQL written in PL/pgSQL. Provides a large library of... | You have a Postgres database with non-trivial schema, constraints, functions, RLS policies, or migrations... | `see repo` | `PostgreSQL` |
| [pg_prove (TAP-Parser-SourceHandler-pgTAP)](https://github.com/theory/tap-parser-sourcehandler-pgtap) | Command-line harness (pg_prove, plus pg_tapgen) that runs pgTAP test scripts under... | You write pgTAP tests and need a runner that executes a directory of .sql (or .pg) test files against a... | `docker pull itheory/pg_prove` | `Artistic-1.0-Perl OR GPL-1.0-or-later` |
| [tSQLt](https://github.com/tSQLt-org/tSQLt) | Unit-testing framework for Microsoft SQL Server, implemented in T-SQL. Runs each test... | You own a SQL Server database with stored procedures, functions, triggers, or complex constraints and want... | `see repo` | `Apache-2.0` |
| [utPLSQL](https://github.com/utPLSQL/utPLSQL) | Unit-testing framework for Oracle PL/SQL and SQL (v3), modeled on JUnit/RSpec. Provides... | You maintain an Oracle database with packages, procedures, and functions and want structured,... | `see repo` | `Apache-2.0` |
| [Jepsen](https://github.com/jepsen-io/jepsen) | Distributed-systems consistency-verification framework with built-in fault injection.... | You run or build a distributed/replicated database or coordination service and need to find consistency... | `apt install default-jdk libjna-java gnuplot graphviz` | `EPL-1.0` |
| [Chaos Mesh](https://github.com/chaos-mesh/chaos-mesh) | CNCF cloud-native chaos-engineering platform for Kubernetes. Injects faults via CRDs:... | Your database runs on Kubernetes and you want to verify resilience/HA and data integrity under realistic... | `see repo` | `Apache-2.0` |
| [MariaDB randgen (RQG / Random Query Generator)](https://github.com/MariaDB/randgen) | The classic MySQL/MariaDB Random Query Generator with MariaDB patches. Uses grammar... | You test a MySQL/MariaDB-compatible server and want grammar-driven, multi-threaded randomized workloads to... | `see repo` | `GPL-2.0` ⚠️ |
| [go-sqlsmith](https://github.com/PingCAP-QE/go-sqlsmith) | Go port/reimplementation of sqlsmith that generates random MySQL-dialect SQL (SELECT... | You build a MySQL-compatible engine in Go (e.g. TiDB-like) and want an embeddable random query generator for... | `go get github.com/PingCAP-QE/go-sqlsmith` | `Apache-2.0` |
| [datafusion sqlfuzz (andygrove/sqlfuzz)](https://github.com/andygrove/sqlfuzz) | CLI that generates random Parquet test data and random SQL queries (configurable join... | You build or embed a SQL query engine (especially DataFusion/Spark-style) and want differential testing: run... | `cargo install sqlfuzz` | `Apache-2.0` |
| [go-randgen](https://github.com/pingcap/go-randgen) | Go reimplementation of MySQL randgen that generates SQL from BNF grammar (.yy) and data... | You test a MySQL-compatible engine and want lightweight BNF-grammar-driven random SQL plus built-in two-DSN... | `go install github.com/pingcap/go-randgen/cmd/go-randgen@late` | `NOASSERTION` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
