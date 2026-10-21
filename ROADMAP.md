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
