# Chaos engineering & fault injection

Inject latency, faults, resource pressure.

**Reach for this when:** a service runnable under docker-compose / deps to perturb.

_14 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [Chaos Mesh](https://github.com/chaos-mesh/chaos-mesh) | CNCF cloud-native chaos engineering platform for Kubernetes. Injects pod faults... | You run a Kubernetes-based service and want to verify resilience to pod crashes, network partitions, slow... | `see repo` | `Apache-2.0` |
| [LitmusChaos](https://github.com/litmuschaos/litmus) | CNCF incubating chaos engineering platform with a control plane (ChaosCenter) and a... | Kubernetes teams that want reusable, CI/CD-integrated chaos experiments with a UI and a catalog of... | `see repo` | `Apache-2.0` |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | A TCP proxy by Shopify that deterministically injects network conditions ('toxics') such... | Integration/end-to-end tests where you point your app at a proxied dependency to reproduce flaky-network... | `docker run -d -p 8474:8474 -p 6379:6379 ghcr.io/shopify/toxi` | `MIT` |
| [Pumba](https://github.com/alexei-led/pumba) | Chaos testing and network emulation CLI for Docker / containerd / Podman containers. Can... | Docker Compose or plain-container setups (no Kubernetes) where you want to test how a service tolerates a... | `see repo` | `Apache-2.0` |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | System stress/load generator with 370+ stressors exercising CPU, cache, memory, VM, I/O,... | Any host or container where you need to simulate resource exhaustion (CPU saturation, memory pressure, disk... | `apt-get install -y stress-ng` | `GPL-2.0` ⚠️ |
| [chaoskube](https://github.com/linki/chaoskube) | Lightweight controller that periodically kills random pods in a Kubernetes cluster.... | Kubernetes deployments where you want continuous, low-config baseline chaos to validate that services... | `see repo` | `MIT` |
| [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) | Vendor-neutral CLI for declarative chaos experiments defined in JSON/YAML. Each... | When you want experiments as code in CI/CD across mixed infrastructure (cloud + k8s + on-prem) with... | `pip install -U chaostoolkit chaostoolkit-kubernetes` | `Apache-2.0` |
| [Chaos Monkey (Netflix)](https://github.com/Netflix/chaosmonkey) | The original chaos engineering tool: randomly terminates VM instances/containers in... | Teams already using Spinnaker for continuous delivery who want scheduled, production-grade instance... | `go install github.com/netflix/chaosmonkey/cmd/chaosmonkey@la` | `Apache-2.0` |
| [PowerfulSeal](https://github.com/bloomberg/powerfulseal) | Bloomberg's chaos tool for Kubernetes. Runs YAML-defined policy scenarios that kill... | Kubernetes clusters where you need scripted experiments that combine pod AND node-level failure with... | `pip install powerfulseal` | `Apache-2.0` |
| [kube-monkey](https://github.com/asobti/kube-monkey) | Chaos Monkey for Kubernetes: an opt-in controller that randomly deletes pods of enrolled... | Kubernetes shops wanting controlled, consent-based pod-kill chaos during business hours, scoped to apps that... | `see repo` | `Apache-2.0` |
| [Krkn (kraken)](https://github.com/krkn-chaos/krkn) | CNCF sandbox chaos and resiliency tool for Kubernetes/OpenShift. Runs scenario-driven... | Kubernetes/OpenShift platform teams focused on measuring recovery time and performance-under-failure (not... | `clone + build from source` | `Apache-2.0` |
| [Comcast](https://github.com/tylertreat/comcast) | Host-level network condition simulator that wraps tc/iptables (Linux) and pfctl/ipfw... | Local dev or CI on a single machine where you want to quickly degrade the network for a process/host and... | `go install github.com/tylertreat/comcast@latest` | `Apache-2.0` |
| [Muxy](https://github.com/mefellows/muxy) | Proxy-based chaos tool operating at layers 4/5/7. Sits between client and service and... | Testing a client or service against a misbehaving HTTP dependency in dev/CI - e.g. injecting 500s, malformed... | `docker pull mefellows/muxy` | `MIT` |
| [Chaosd](https://github.com/chaos-mesh/chaosd) | Standalone (non-Kubernetes) fault injection tool from the Chaos Mesh project for... | Bare-metal or VM environments without Kubernetes where you still want Chaos Mesh-style fault injection on a... | `see repo` | `Apache-2.0` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
