# SurvAtlas development roadmap

SurvAtlas is an experimental project exploring an offline-first emergency information tablet. This roadmap shares the project's direction and broad milestones; it does not promise release dates.

## Current stage — Software prototype

**Status: In development**

The software prototype brings together a dashboard, locally available information, maps, and an on-device AI assistant. A separate OS prototype is being developed to provide a branded startup and kiosk-style application experience.

Recent progress includes:
- A branded startup and loading experience
- Automatic launch into the local application dashboard
- Integration work for a locally running AI assistant
- Code-quality improvements and a successful local production build
- Ongoing refinement of navigation, search, saved places, and device status

This is a software milestone, not a finished physical tablet or a production-ready release.

## Milestone 1 — Repeatable offline demonstration

**Status: Verification in progress**

- Document and repeat tests of core workflows without internet access
- Record supported features, limitations, and failure cases
- Check that startup and core workflows behave consistently after restart
- Publish a demonstration only when its claims are supported by repeatable evidence

## Milestone 2 — Physical tablet prototype

**Status: Planned**

- Deploy the software on the intended physical hardware
- Integrate the touchscreen, storage, power system, and enclosure
- Evaluate the startup experience and everyday usability on-device
- Document hardware-specific constraints and remaining work

## Milestone 3 — Performance and reliability

**Status: Planned**

- Measure system resource use under representative workloads
- Evaluate thermal behavior and battery endurance
- Test recovery from restarts and service failures
- Improve readability, touch interaction, and accessibility

## Milestone 4 — Public demonstration

**Status: Planned**

- Share product-focused screenshots and a demonstration of verified features
- Publish clear test scope and limitations
- Report progress without exposing private implementation details
- Decide on a public preview release when the demonstrated scope is ready

## How progress is reported

Public updates describe product goals and verified milestones. Implementation details, private source code, and internal deployment configuration are intentionally not part of this public showcase.

There is **no announced release date**. Milestones will advance as implementation and testing support them.

SurvAtlas is experimental. It is **not a certified medical device, emergency communications service, or substitute for professional emergency guidance**. Medical and AI-generated information requires independent validation.

[Back to the project overview](README.md)
