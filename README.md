# SurvAtlas

**Offline-first survival intelligence platform**

SurvAtlas is an independently developed project exploring access to practical information, offline maps, navigation, and local AI when an internet connection is unavailable.

> **Project status:** Active development. This repository is a public showcase and documentation hub, not the application's source-code repository.

## What I'm building

- **Offline maps:** MapLibre-based mapping with locally stored map data.
- **Offline routing:** Valhalla navigation service.
- **Local AI:** Ollama integration for on-device assistance and code generation.
- **Reference library:** Offline survival and medical content, with work on integrating local knowledge resources.
- **ARM64 deployment:** Containerized testing toward low-power single-board computers.

## Technology

Next.js 16 · React · TypeScript · SQLite · Docker · ARM64 · MapLibre · Valhalla · Ollama · Kiwix

## Development progress

- [x] Implemented core Next.js application and offline-first components.
- [x] Set up ARM64 Docker testing on an x86 Windows host.
- [x] Completed a successful ARM64 production build and TypeScript validation.
- [x] Started the production server successfully.
- [x] Collected initial application and routing-service resource measurements.
- [ ] Validate complete offline functionality end to end.
- [ ] Benchmark the full AI model's memory and CPU usage.
- [ ] Test on physical ARM64 hardware.

## ARM64 performance snapshot — October 21, 2026

| Component | Observed RAM |
| --- | ---: |
| SurvAtlas (Next.js production container) | ~400 MiB |
| Valhalla routing container | ~118 MiB |
| **Combined observed container memory** | **~518 MiB** |

The SurvAtlas container was configured with a **6 GiB RAM limit and 4 CPU limit**. One captured CPU reading was **66.15%** in Docker's per-core accounting. The production server reported readiness in **2.5 seconds** after the build completed.

**Measurement limitations:** These are snapshots, not a sustained peak-memory benchmark. Tests used x86-hosted ARM64 emulation; performance cannot be directly extrapolated to an Orange Pi. Ollama was running outside the containers on the Windows host, so **AI model memory is excluded** from the figures above. Full offline functionality remains to be validated.

## Repository policy

This public repository contains only project information and selected non-sensitive documentation. Application source code, local datasets, credentials, environment files, and private configurations are not published here.

## Roadmap

1. Complete end-to-end offline tests for mapping, routing, AI, and reference content.
2. Measure memory and latency under realistic concurrent workloads.
3. Evaluate deployment on physical ARM64 hardware.
4. Improve reliability, usability, and offline resource management.

---

*SurvAtlas is an ongoing personal engineering project. Benchmarks and feature status will be updated as testing progresses.*
