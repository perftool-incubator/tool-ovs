# OVS Tool

## Purpose
Collects and post-processes Open vSwitch (OVS) and Open Virtual Network (OVN) performance data during benchmark execution. Captures bridge configurations, flow tables, PMD thread statistics, coverage counters, and memory usage.

## Language
Bash — all scripts (collection, start/stop, post-processing)

## Key Files
| File | Purpose |
|------|---------|
| `ovs-collect` | Main collection loop: dumps flows, appctl stats, coverage/memory data at configurable intervals |
| `ovs-start` | Parses `--interval` parameter (default: `3`), launches ovs-collect in background |
| `ovs-stop` | Kills collector, compresses output with xz |
| `ovs-post-process` | Converts raw OVS data to CDM-compliant compressed output |
| `rickshaw.json` | Rickshaw integration: endpoint allow/block lists, file deployment, post-process script |
| `workshop.json` | Engine image build: compiles OVS 3.3.0 from source |

## Conventions
- Primary branch is `master`
- Runs as a profiler tool on master/worker/profiler/compute roles, blocked on client/server
- Post-processed output conforms to CommonDataModel schema
