<div align="center">

<img src="assets/logo1.jfif" alt="SurvAtlas wordmark and emblem" width="100%" />

# SurvAtlas

### An offline-first emergency information tablet — in development

**Local AI · Offline maps & routing · Reference library · ARM64**

An independent, approximately year-long engineering project exploring how useful information and navigation tools can remain accessible when connectivity cannot be relied upon.

[**Explore the roadmap**](https://github.com/KA-MIS/survatlas/issues) · [**Development progress**](#development-progress) · [**Architecture**](#system-architecture) · [**Performance notes**](#engineering-validation)

</div>

---

> [!IMPORTANT]
> **Project stage: Active research, software development and hardware prototyping.** SurvAtlas is intended to become a portable, battery-powered emergency-preparedness tablet. The **current software runs fully offline**, according to development testing; physical tablet deployment, reproducible external verification, and emergency-readiness validation remain future work. This repository is the **public documentation/showcase**, not the private application source code.

## Why SurvAtlas?

Access to maps, instructions, and reference information often depends on internet connectivity. In an emergency, that dependency can become a serious limitation.

**SurvAtlas aims to put essential digital resources into a self-contained tablet:** a touch-first interface for local maps, routing, survival and medical references, and a locally hosted AI assistant.

The engineering challenge is to bring these components together while keeping the system practical for portable hardware: constrained memory, battery power, offline storage, reliability, and usability under pressure.

**Product vision:** A person should be able to turn on the tablet and access its locally stored resources without relying on a cloud account or active internet connection.

**Current status:** The software's features work without internet access. This is distinct from validating the eventual battery-powered tablet for real-world emergency use.

## Application gallery

> [!CAUTION]
> ### 🔴 DEVELOPMENT BUILD — NOT THE FINAL DESIGN
> **These are real screenshots of the current SurvAtlas development build — not mockups or renders.**
>
> The interface is **functional and actively used for integration, debugging, and testing**. Visual refinement will follow the ongoing reliability and hardware work. **These screenshots do not represent the final tablet design.**

<table>
  <tr>
    <td width="50%" align="center">
      <img src="assets/1.png" alt="SurvAtlas system dashboard with power, storage, and system status" width="100%" />
      <br /><strong>System dashboard</strong><br />Power, storage, status, and quick-access modules
    </td>
    <td width="50%" align="center">
      <img src="assets/2.png" alt="SurvAtlas local coding assistant chat interface" width="100%" />
      <br /><strong>Local coding assistant</strong><br />Chat history, code responses, and local-model integration
    </td>
  </tr>
</table>

<div align="center">
  <img src="assets/3.png" alt="SurvAtlas offline Lithuania map with navigation tools and places categories" width="80%" />
  <br /><strong>Offline mapping interface</strong><br />
  Local Lithuania map data, route-planning controls, and location tools
</div>

<p align="center"><img src="assets/logo2.jfif" alt="SurvAtlas shield emblem" width="110" /></p>

> **Development note:** These screenshots show implemented interfaces. The local AI assistant **works without an internet connection**, but its model performance and responses are **still being tuned and evaluated**. The software operates fully offline, while physical-tablet readiness, medical-information accuracy, and independent reproducible testing remain separate concerns.

## The intended tablet experience

| Capability | User benefit | Current engineering status |
| --- | --- | --- |
| **Offline maps** | Browse locally stored geographic information | Implemented and working offline; formal reproducible test documentation pending |
| **Local route planning** | Calculate routes without relying on online directions | Implemented and working offline; formal reproducible test documentation pending |
| **On-device AI assistant** | Interact with a locally hosted language model | Working fully offline; model quality tuning and performance testing ongoing |
| **Survival reference library** | Consult locally available practical information | Local access works offline; content curation and refinement ongoing |
| **Medical reference access** | Find reference information when connectivity is unavailable | Offline access working; medical content accuracy review ongoing |
| **Portable touchscreen device** | Use the system as a standalone emergency tablet | Hardware integration and battery validation planned |

> [!CAUTION]
> SurvAtlas is an experimental preparedness project. It is **not** a certified medical device, an emergency communications system, or a replacement for emergency services or qualified professional guidance. Reference and AI-generated content must be independently evaluated for accuracy and suitability.

## Technology and engineering scope

| Layer | Technology / approach |
| --- | --- |
| Application | Next.js 16, React, TypeScript |
| Local data | SQLite |
| Mapping | MapLibre and locally stored map resources |
| Routing | Valhalla |
| Local AI | Ollama |
| Knowledge resources | Local survival/medical content; Kiwix-oriented integration |
| Packaging | Docker |
| Target platform | ARM64 single-board computing hardware |
| Product form factor | Portable, touch-first tablet concept |

### System architecture

```text
                   SURVATLAS EMERGENCY TABLET
                  (planned physical device)
                               |
                     Touchscreen interface
                               |
                     SurvAtlas application
                     Next.js / TypeScript
                               |
          +--------------------+--------------------+
          |                    |                    |
     Local knowledge       Mapping & routing      Local AI
    SQLite / references    MapLibre / Valhalla     Ollama
          |                    |                    |
          +--------------------+--------------------+
                               |
                      Local compute & storage
                       ARM64 deployment goal
                               |
                        Battery / enclosure
                         (planned hardware)
```

*Conceptual architecture. Individual services and datasets may run as separate processes or containers. The physical tablet is not presented as a completed implementation.*

## Development progress

### Built through approximately one year of iteration

SurvAtlas has progressed through application development, offline-service integration, local AI experimentation, and deployment testing. **The first GitHub source commit is not the project start date**: substantial work took place locally before the repository was established.

| Engineering stage | Work undertaken | Evidence / next step |
| --- | --- | --- |
| **Foundation** | Next.js application, TypeScript, user interfaces, local data integration | Core application developed |
| **Offline information** | Mapping, routing, survival and medical content workflows | Offline operation reported working; document reproducible test coverage |
| **Local intelligence** | Ollama-backed assistant integration | Offline behavior working; tune model quality and benchmark resources |
| **Deployment research** | Docker packaging and ARM64 build experiments | Successful emulated ARM64 build and production startup |
| **Portable hardware** | Investigating the requirements of a self-contained tablet | Physical integration, battery and endurance testing remain |

The roadmap tracks **readiness and verification**, rather than announcing dates that have not been established.

## Verified development milestones

The following milestones are **completed engineering work**, recorded retrospectively because SurvAtlas was developed locally before its public GitHub showcase was established.

| Completed work | Evidence in public tracking |
| --- | --- |
| Core Next.js / TypeScript application and local-data foundation | [#6 — Application foundation](https://github.com/KA-MIS/survatlas/issues/6) · Completed |
| MapLibre mapping and Valhalla routing component integration | [#7 — Maps & routing](https://github.com/KA-MIS/survatlas/issues/7) · Completed |
| Ollama local AI integration and initial reference workflows | [#8 — Local AI & knowledge](https://github.com/KA-MIS/survatlas/issues/8) · Completed |
| Successful emulated ARM64 production build, TypeScript validation, and initial measurements | [#9 — ARM64 build & snapshot](https://github.com/KA-MIS/survatlas/issues/9) · Completed |

**What completed means here:** These are implementation or initial-test milestones, **not** confirmation that the finished tablet has passed emergency-readiness testing or that independent offline test evidence and complete AI benchmarks have been published. The open issues below track that remaining work.

## Public engineering roadmap

Each workstream below is a real GitHub issue with acceptance criteria. This makes the plan inspectable and allows progress to be documented as testing and implementation continue.

| Priority | Workstream | Tracking |
| --- | --- | --- |
| 01 | Document and independently reproduce complete offline operation | [Issue #1 — Offline emergency workflows](https://github.com/KA-MIS/survatlas/issues/1) |
| 02 | Prototype the physical ARM64 emergency tablet | [Issue #2 — Tablet hardware](https://github.com/KA-MIS/survatlas/issues/2) |
| 03 | Benchmark performance, thermals, and battery endurance | [Issue #3 — Performance & power](https://github.com/KA-MIS/survatlas/issues/3) |
| 04 | Refine the touch-first emergency user experience | [Issue #4 — Reliable interface](https://github.com/KA-MIS/survatlas/issues/4) |
| 05 | Publish a reproducible demonstration and technical documentation | [Issue #5 — Demo & documentation](https://github.com/KA-MIS/survatlas/issues/5) |

**Near-term focus:** Document and reproduce the already working offline workflows, measure the *complete* application stack including local AI, and prepare deployment to physical ARM64 hardware.

**Longer-term focus:** Validate a portable device's power system, thermal behavior, storage, accessibility, startup/recovery behavior, and reliability in representative use cases.

[**View all roadmap tasks →**](https://github.com/KA-MIS/survatlas/issues)

## Engineering validation

### Initial ARM64 test snapshot · 21 October 2026

An ARM64 container build was tested through emulation on an x86 Windows host. The Next.js production build and TypeScript validation completed successfully, and the production server started.

| Observed component | Memory at capture |
| --- | ---: |
| SurvAtlas application container | ~400 MiB |
| Valhalla routing container | ~118 MiB |
| **Combined container snapshot** | **~518 MiB** |

Additional observations:

- Application container configured with a **6 GiB RAM limit** and **4 CPU limit**.
- One Docker CPU sample reported **66.15%** using Docker's per-core accounting.
- Production server readiness was reported in **2.5 seconds** following build completion.

**Limitations:** These figures are snapshots, not peak or sustained-load measurements. They come from **ARM64 emulation**, not a physical tablet or single-board computer. **Ollama ran outside the containers on the Windows host**, so its model memory is **excluded**. Battery life, total device power draw, and thermal performance have **not** been established by these measurements. Offline functionality is reported working in development, but this benchmark snapshot is not itself an offline test report.

Publishing both the results and their limitations is part of the project's engineering approach.

## Design priorities

**Offline independence.** The current software works without an internet connection; preserve and systematically test this capability through future releases.

**Resource-conscious integration.** Treat local AI, routing, and map datasets as a combined hardware and software budget.

**Human-centered emergency use.** Prioritize readability, straightforward navigation, touch interaction, and clear system status.

**Reliability over feature count.** Test what happens when services fail, resources run low, or the device restarts.

**Transparent verification.** Separate working integrations, experimental features, and future goals.

## About this repository

This repository serves as the **public SurvAtlas project portfolio** for engineers, recruiters, and interested collaborators. It documents the concept, engineering choices, development journey, tests, and roadmap.

The **application source code is maintained in a separate private repository**. This showcase does not distribute private configuration, credentials, model files, or large local datasets.

A technical walkthrough or source-code review can be discussed on request, subject to access approval.

### What will be added next?

- Additional application screenshots and physical tablet-prototype photographs when available.
- A concise demonstration video showing verified features.
- Repeatable benchmark and offline test procedures.
- Physical ARM64 hardware measurements and an architecture deep dive.

---

<div align="center">

<img src="assets/logo2.jfif" alt="SurvAtlas shield emblem" width="130" />

**SurvAtlas** · Independent engineering project · Active development

Maintained by [KA-MIS](https://github.com/KA-MIS) · **Contact:** [info@survatlas.com](mailto:info@survatlas.com)

*Building toward an offline-first emergency tablet, one verified milestone at a time.*

</div>
