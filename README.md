# SurvAtlas

### Emergency-ready tablet concept · Offline intelligence · Local AI · Navigation

**An independent software engineering project developed over approximately one year.**

**SurvAtlas is being developed as the software foundation for a portable emergency-preparedness tablet.** The intended device would give people access to locally stored survival and medical references, maps, navigation, and an AI assistant when internet access is limited, unreliable, or unavailable.

The tablet is the **product vision**, not a completed or safety-certified device. The current work centers on software integration, offline validation, and preparation for physical ARM64 hardware.

The project has evolved through sustained development, integration work, and deployment experiments—not a one-day prototype. It is an ongoing engineering effort focused on practical offline computing, resource efficiency, and reliable access to information.

> **Status:** Active development and system validation  
> **Repository:** Public project showcase and engineering documentation. Application source code is maintained separately in a private repository.  
> **Last documented test snapshot:** 21 October 2026

---

## Project at a glance

| Area | Engineering focus |
| --- | --- |
| Application | Next.js 16, React, TypeScript |
| Data | SQLite and local-first data access |
| Mapping | MapLibre with locally stored map resources |
| Routing | Valhalla routing service |
| AI | Ollama-based local inference integration |
| Knowledge | Survival and medical reference content; Kiwix integration work |
| Deployment | Docker, ARM64 container builds and emulated testing |
| Product vision | Portable, touch-first emergency-preparedness tablet |
| Target direction | Resource-conscious deployment on ARM64 single-board computers |

## The tablet vision

The long-term goal is a self-contained, battery-powered tablet that people can use to consult essential information and navigate during emergencies. The intended experience prioritizes fast access to locally available resources, a touch-friendly interface, and operation without routine dependence on cloud services.

**The physical tablet, battery system, and end-to-end emergency workflows remain development goals.** SurvAtlas is not currently represented as a validated emergency communications system, medical device, or substitute for professional emergency services.

## The engineering challenge

Many modern applications assume permanent connectivity and cloud-hosted services. SurvAtlas explores a different architecture: keeping important functionality and reference materials accessible locally.

This requires more than building a web interface. The project involves coordinating services with different resource requirements, handling offline datasets, integrating locally hosted AI, packaging application components, and testing behavior under hardware constraints.

**Core design principles**

- **Offline-first:** Prioritize local availability rather than depending on a remote service for every interaction.
- **Modular architecture:** Separate the application, routing, AI, and knowledge resources into manageable components.
- **Hardware awareness:** Evaluate memory, CPU, storage, and deployment trade-offs.
- **Practical usability:** Make complex offline capabilities accessible through a unified interface.
- **Evidence-led development:** Distinguish implemented components from functionality that still needs end-to-end verification.

## What has been built

### Application and interface
A Next.js/TypeScript application with interfaces for survival information, medical references, maps, assistant interactions, and related tools.

### Offline maps and routing
MapLibre integration for locally available mapping resources, alongside a Valhalla routing service. Complete disconnected, end-to-end behavior remains a validation target.

### Local AI
Ollama integration to explore on-device assistance without requiring a cloud-hosted language model. Full-model resource benchmarking and comprehensive offline testing are still in progress.

### Reference and knowledge resources
Work on organizing survival and medical content and connecting local reference resources, including a Kiwix-oriented offline knowledge workflow.

### ARM64 deployment experiments
Containerized ARM64 testing on an x86 Windows host, including a successful production build, TypeScript validation, production-server startup, and initial resource measurements.

---

## Development journey

**Approximately one year of iterative development**

SurvAtlas has been developed across multiple stages of design, implementation, integration, and testing. The stages below describe the project's engineering progression; they are **not claimed to be individually dated milestones**.

| Stage | Focus | Progress |
| --- | --- | --- |
| **01 — Foundation** | Establish the application structure, TypeScript stack, interfaces, and local data approach | Implemented |
| **02 — Offline capabilities** | Integrate mapping, routing, and reference-content workflows | Implemented components; full offline validation pending |
| **03 — Local intelligence** | Connect locally hosted AI and assistant functionality | Integration implemented; comprehensive benchmarking pending |
| **04 — Systems engineering** | Package services, test ARM64 builds, and investigate runtime resource use | Initial emulated ARM64 tests completed |
| **05 — Hardware and reliability** | Validate on physical ARM64 hardware and under realistic disconnected workloads | Planned / in progress |

This is a continuing project: its public Git history does not represent the full period of development. The code was developed locally before the first GitHub source snapshot was published.

## Technical validation

### ARM64 performance snapshot — 21 October 2026

The following figures were observed during initial container testing on an x86 Windows host using ARM64 emulation.

| Component | Observed memory |
| --- | ---: |
| SurvAtlas / Next.js production container | ~400 MiB |
| Valhalla routing container | ~118 MiB |
| **Combined observed container memory** | **~518 MiB** |

Additional observations:

- The SurvAtlas container was configured with a **6 GiB memory limit** and **4 CPU limit**.
- A captured Docker CPU reading was **66.15%** in Docker's per-core accounting.
- The production server reported readiness in **2.5 seconds** after the build completed.
- The ARM64 production build and TypeScript validation succeeded.

**How to interpret these results:** These values are initial snapshots, not sustained load or peak-memory benchmarks. The environment used ARM64 emulation, so results should not be treated as measurements from a physical single-board computer. Ollama ran separately on the Windows host, meaning **AI model memory is not included** in the container figures. Complete offline operation has not yet been verified end to end.

---

## Engineering roadmap

The roadmap is organized by **technical readiness**, rather than speculative release dates. Track the major workstreams through [GitHub Issues](https://github.com/KA-MIS/survatlas/issues); each issue has concrete acceptance criteria.

| Workstream | Tracking issue | State |
| --- | --- | --- |
| Offline emergency workflows | [#1 — Disconnected operation](https://github.com/KA-MIS/survatlas/issues/1) | Planned validation |
| Physical emergency tablet | [#2 — Hardware prototype](https://github.com/KA-MIS/survatlas/issues/2) | Planned |
| Performance and power | [#3 — Benchmarks and battery](https://github.com/KA-MIS/survatlas/issues/3) | Planned |
| Emergency-focused interface | [#4 — Reliable UX](https://github.com/KA-MIS/survatlas/issues/4) | Planned |
| Demo and documentation | [#5 — Technical showcase](https://github.com/KA-MIS/survatlas/issues/5) | Planned |

A GitHub Projects board can organize these issues into **Todo / In progress / Done** columns.

### Phase 1 — Offline validation
- [ ] Test the application with external network connectivity disabled.
- [ ] Verify local maps and routing with representative offline datasets.
- [ ] Validate assistant behavior with local AI services only.
- [ ] Verify access to reference materials without internet connectivity.
- [ ] Document setup requirements and reproducible test procedures.

### Phase 2 — Performance and resilience
- [ ] Benchmark AI model memory, CPU usage, and response latency.
- [ ] Measure total system resources under concurrent workloads.
- [ ] Investigate startup time, service recovery, and failure behavior.
- [ ] Improve dataset handling, storage usage, and offline resource management.

### Phase 3 — Physical ARM64 emergency tablet
- [ ] Define the tablet hardware, display, power, and battery requirements.
- [ ] Deploy to a physical ARM64 single-board computer.
- [ ] Compare real-hardware results with emulated benchmarks.
- [ ] Test thermal behavior, battery endurance, sustained performance, and practical resource limits.
- [ ] Refine container configuration for the target hardware.

### Phase 4 — Product quality
- [ ] Improve accessibility, usability, and small-screen interactions.
- [ ] Expand automated testing and operational documentation.
- [ ] Establish a repeatable release and versioning workflow.
- [ ] Prepare a public demonstration of the tested feature set.

*Roadmap items are development goals, not promises of delivery dates or claims of completed functionality.*

## Architecture overview

```text
                     SurvAtlas application
                     Next.js · TypeScript
                              |
             +----------------+----------------+
             |                |                |
       Local data       Offline mapping    Local assistant
         SQLite            MapLibre            Ollama
                              |
                           Routing
                           Valhalla
                              |
                     Local knowledge and
                     reference resources
```

The diagram is a conceptual overview; individual services and datasets may run in separate processes or containers.

## Project ownership and access

SurvAtlas is an **independently developed personal engineering project**. This public repository exists to document the design, development progress, technical decisions, and test results for interested engineers, recruiters, and potential collaborators.

The implementation is maintained in a **separate private source repository**. Local datasets, model files, credentials, and other environment-specific assets are not distributed through this showcase.

**Technical review:** Source-code access or a guided project walkthrough can be discussed upon request.

## Next documentation milestones

This showcase will become more useful as the project matures. Planned additions include application screenshots, a short feature demonstration, reproducible performance results, and a more detailed architecture walkthrough.

---

**Maintainer:** [KA-MIS](https://github.com/KA-MIS)  
**Project:** SurvAtlas  
**Focus:** Emergency tablet systems, full-stack software engineering, offline-first architecture, local AI integration, and ARM64 deployment.

*SurvAtlas is under active development. Feature descriptions and measurements reflect the current documented state and will be updated as validation progresses.*
