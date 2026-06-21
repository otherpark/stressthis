# DAST / web security scanning

Dynamically probe a running web app (authorized only).

**Reach for this when:** a running, in-scope web app you own/are authorized to test.

_12 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [OWASP ZAP (Zed Attack Proxy)](https://github.com/zaproxy/zaproxy) | Full-featured DAST proxy/scanner that spiders a web app, passively analyzes traffic, and... | Use when you have a running web app/staging URL and want broad, general-purpose DAST coverage across the... | `docker run -t zaproxy/zap-stable zap-baseline.py -t https://` | `Apache-2.0` |
| [Nuclei](https://github.com/projectdiscovery/nuclei) | Fast, template-driven vulnerability scanner built on a YAML DSL. Ships 12k+ community... | Use when you want to check a deployed app/API/host for known CVEs and exposures rather than fuzz for novel... | `go install -v github.com/projectdiscovery/nuclei/v3/cmd/nucl` | `MIT` |
| [sqlmap](https://github.com/sqlmapproject/sqlmap) | Automated SQL injection detection and exploitation tool. Fingerprints the DBMS, confirms... | Use when a target has database-backed endpoints and you specifically want to find/confirm SQL injection (and... | `clone + build from source` | `GPL-2.0-or-later` ⚠️ |
| [Nikto](https://github.com/sullo/nikto) | Classic web server scanner that checks for thousands of dangerous/outdated server files,... | Use for a quick first-pass recon of a web server: outdated server software, leftover/dangerous files,... | `docker run --rm sullo/nikto -h https://target.example.com` | `GPL-3.0-only` ⚠️ |
| [Wapiti](https://github.com/wapiti-scanner/wapiti) | Black-box web application vulnerability scanner. Crawls the app to extract links and... | Use when you have a deployed app and want active fuzzing of forms/parameters for injection-class bugs... | `pip install wapiti3` | `GPL-2.0-only` ⚠️ |
| [dalfox](https://github.com/hahwul/dalfox) | Specialized, fast XSS scanner and parameter analysis tool. Discovers parameters,... | Use when you specifically want high-quality XSS detection on a set of URLs/parameters, especially in a recon... | `go install github.com/hahwul/dalfox/v2@latest` | `MIT` |
| [ffuf](https://github.com/ffuf/ffuf) | Fast web fuzzer in Go. Drives content/directory discovery, virtual-host discovery,... | Use to discover unlinked endpoints, hidden directories/files, vhosts, or to brute-force parameter names that... | `go install github.com/ffuf/ffuf/v2@latest` | `MIT` |
| [feroxbuster](https://github.com/epi052/feroxbuster) | Fast recursive content-discovery / forced-browsing tool in Rust. Brute-forces... | Use for thorough recursive directory/file enumeration to surface unlinked content (backups, source, admin... | `cargo install feroxbuster` | `MIT` |
| [katana](https://github.com/projectdiscovery/katana) | Next-generation crawling and spidering framework. Supports standard HTTP crawling and... | Use as the recon/attack-surface-mapping front end of a DAST pipeline: crawl the app to enumerate all URLs... | `go install github.com/projectdiscovery/katana/cmd/katana@lat` | `MIT` |
| [commix](https://github.com/commixproject/commix) | Automated OS command injection detection and exploitation tool. Tests parameters for... | Use when a target passes user input into system commands (file processors, ping/diagnostic features, upload... | `clone + build from source` | `GPL-3.0-or-later` ⚠️ |
| [XSStrike](https://github.com/s0md3v/XSStrike) | Cross-site scripting detection suite with hand-written HTML/JS parsers, a context-aware... | Use for focused, context-aware XSS hunting on specific endpoints/parameters when you want smarter payload... | `clone + build from source` | `GPL-3.0-only` ⚠️ |
| [testssl.sh](https://github.com/drwetter/testssl.sh) | Single-script tool that probes any TLS/SSL service (any port) for supported protocols... | Use to audit the transport-layer security of a web app's HTTPS endpoint (or any TLS service): weak ciphers,... | `docker run --rm drwetter/testssl.sh https://target.example.c` | `GPL-2.0-only` ⚠️ |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
