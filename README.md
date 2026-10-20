# User Carbon Footprint Tools Evaluation

*A review of carbon footprint tools for digital research infrastructure. For full evaluation comments and remarks, please view or download the `tools-comparison.csv` file in this repository.*

## 1. Technical Overview
| Tool | Primary use case | Language / interface | Scheduler / platform |
|---|---|---|---|
| **Green Algorithms (GA4HPC)** | Post-hoc energy & carbon estimation | Bash script | SLURM (adaptable) |
| **ARCHER2 Emissions Tools** | Per-job/user emissions reporting | CLI tools / Python | SLURM (ARCHER2 only) |
| **CodeCarbon** | Tracking CO2 of arbitrary Python workloads | Python library (embed) | No HPC scheduler support |
| **CEEMS** | Operator-level energy/emissions stack | eBPF, Grafana | SLURM, OpenStack, K8s |
| **GUILT (STFC)** | Carbon emission logging | Rust CLI + Shell | SLURM |
| **GRACE (Bristol)** | Footprint estimation (Scope 2 + 3) | Python package / CLI | SLURM |
| **Carbon (Imperial)** | Per-job carbon estimation | Python CLI | PBS |
| **CarbonTracker** | Energy/carbon for deep learning | Python lib + CLI | SLURM, NVML, RAPL |
| **nvidia-co2** | Real-time GPU CO2 display | Python CLI | NVIDIA GPUs only |
| **nf-co2footprint** | Nextflow pipeline tracking | CLI flag | Slurm |

## 2. Tracking Capabilities
| Tool | Job script integration | Carbon intensity? | Scope 3 (embodied)? | Language-agnostic? |
|---|---|---|---|---|
| **GA4HPC** | Reads logs post-hoc | Estimated | No | Yes |
| **ARCHER2 Tools** | `sacct` / `jobemissions` | Real-time (API) | Yes (Hardware LCA) | Yes |
| **CodeCarbon** | None | Average intensity | No | Python only |
| **CEEMS** | Not explicitly stated | Real-time factors | If available | Yes |
| **GUILT** | Not explicitly stated | Not explicitly stated| Not stated | Yes |
| **GRACE** | Reads accounting logs | Real-time (API) | Yes (Isambard/ARCHER2)| Yes |
| **Carbon (Imperial)**| `carbon <jobID>` post-hoc | Real-time (API) | Not stated | Yes |
| **CarbonTracker** | CLI wrap / SLURM-aware | Location-aware | No | CLI wrap only |
| **nvidia-co2** | None | Static IP geolocation | No | GPU-only |
| **nf-co2footprint** | Launch command flag | Real-time via API | Yes | Yes |
