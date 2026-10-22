# SurvAtlas release roadmap

SurvAtlas is an experimental offline-first emergency information platform. This roadmap describes **planned readiness milestones**, not promised release dates. Features already working in development are distinguished from verification still required.

The [public issue tracker](https://github.com/KA-MIS/survatlas/issues) contains the detailed work items and acceptance criteria.

## Milestone 0 — Working offline software (development baseline)

**Status: Implemented in development; external verification pending**

- Next.js/TypeScript interface and local data integration
- Offline map browsing and Valhalla routing
- Local Ollama assistant and offline reference workflows
- Initial Docker packaging and emulated ARM64 build

These milestones represent functional development work, **not** a validated physical emergency tablet. See [completed milestones](https://github.com/KA-MIS/survatlas/issues?q=is%3Aissue+is%3Aclosed).

### 22 October 2026 — Development baseline verification update

The working application baseline has advanced beyond initial feature integration:

- **Code quality:** Eight reported ESLint errors were resolved; `npm run lint -- --quiet` passed locally.
- **Type safety:** `npx tsc --noEmit` passed locally.
- **Production packaging:** Next.js 16.2.10 `npm run build` completed successfully in the Debian development VM.
- **UI and state improvements:** AI/coding assistant error handling, battery status typing, navigation, saved-place synchronization, and survival search input were updated.
- **OS integration:** A Debian 13 x86-64 VirtualBox kiosk prototype now boots into a branded splash and launches a local Chromium application session, with systemd-managed app and `llama.cpp` services and a dashboard readiness signal.

**Evidence:** [Application fix commit `3657a0e`](https://github.com/KA-MIS/survatlas-development/commit/3657a0e) · [SurvAtlas OS prototype](https://github.com/KA-MIS/survatlas-os) · [Public development notes](README.md#development-progress).

**Still required:** GitHub Actions result confirmation, hands-on regression tests of affected UI flows, reproducible offline end-to-end test procedures, and validation on actual ARM64 tablet hardware. A successful local build is not a release-readiness or emergency-safety certification.

## Milestone 1 — Reproducible offline software demonstration

**Status: Planned verification work**

- Publish a repeatable offline test procedure covering maps, routing, references and AI
- Document the precise services, datasets, and hardware used
- Demonstrate startup and core workflows without connectivity
- Record failure cases and known limitations

Tracking: [#1 — Offline emergency workflows](https://github.com/KA-MIS/survatlas/issues/1), [#5 — Demo & documentation](https://github.com/KA-MIS/survatlas/issues/5)

## Milestone 2 — Physical ARM64 prototype

**Status: Planned**

- Deploy the full stack on actual ARM64 hardware
- Integrate touch display, storage, power system and enclosure
- Measure startup, service recovery and usability on the device
- Document integration decisions and constraints

Tracking: [#2 — Tablet hardware](https://github.com/KA-MIS/survatlas/issues/2)

## Milestone 3 — Performance and reliability evaluation

**Status: Planned**

- Measure full-system RAM and CPU usage, including local AI
- Test thermals and battery endurance under representative loads
- Validate core workflows after restart and service failure
- Improve touch interaction, readability and accessibility

Tracking: [#3 — Performance & power](https://github.com/KA-MIS/survatlas/issues/3), [#4 — Reliable interface](https://github.com/KA-MIS/survatlas/issues/4)

## Milestone 4 — Public technical demonstration

**Status: Planned**

- Publish a demonstration of verified functionality
- Share hardware photos, test methodology, and measured results
- Document remaining limitations and unresolved risks
- Decide whether a named preview release is warranted based on evidence

Tracking: [#5 — Demo & documentation](https://github.com/KA-MIS/survatlas/issues/5)

## Release policy

There is **no announced release date or production-ready version**. Milestones advance only when their evidence and acceptance criteria are documented. Release names or tags, if introduced, will reflect verified scope rather than marketing deadlines.

SurvAtlas is **not a certified medical device, emergency communications service, or substitute for professional emergency guidance**. Medical and AI-generated information requires independent validation.

[Back to project overview](README.md)
