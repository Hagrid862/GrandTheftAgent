# GrandTheftAgent project constraints

This document records the starting assumptions for [M0.01](https://github.com/Hagrid862/GrandTheftAgent/issues/1). The [project backlog](../BACKLOG.md) describes the milestones and their acceptance criteria. The [GitHub project](https://github.com/users/Hagrid862/projects/4) tracks the work and its results.

## Budget and time

- Aim for **PLN 0 in new spending through M1**, the first playable prototype. Use the existing ChatGPT/Codex access for development work.
- Use the existing Mac for builds and testing. Defer hardware purchases, cloud build capacity, and paid assets while local options meet the needs of the current milestone.
- Use subtitles or temporary audio in M1. Consider a short paid voice subscription, such as ElevenLabs, once an approved scene needs spoken dialogue. Finalize the script, estimate generation and revision needs, and check the chosen plan's usage rights before committing to it. Keep the license and generation details with any audio intended for release. [ElevenLabs billing and licensing](https://elevenlabs.io/docs/overview/administration/billing)
- Voice production, localization, and external playtesting remain possible later costs. The project owner approves any new spend before it is incurred.
- The project owner has not committed to a fixed number of hours per week. Use the work completed in M0 to estimate what the owner needs to review and agree on the effort limit for the M1 session.

## Hardware and platforms

| Hardware | Current role | Follow-up |
| --- | --- | --- |
| Mac Studio, Apple M3 Ultra, 96 GB RAM | Primary development machine and initial macOS build and test machine. The project volume had 87 GiB free on 2026-11-22. | Measure disk usage during the first build. Choose the reference hardware for M2 before collecting performance results. |
| Retail PS5 Pro | Reference for how released games handle controls, camera movement, and perceived performance. PlayStation remains a release candidate. | Revisit after M2. Running our own Unreal build requires the Sony developer approval process and access to the relevant Unreal console tools. [Epic Games console development guide](https://dev.epicgames.com/community/learning/knowledge-base/B9xk/getting-started-with-console-development-for-unreal-engine-and-epic-online-services) |

These are the two currently available devices. Access to a lower-spec test machine remains open. If the M2 reference setup needs one, first check whether a suitable machine can be borrowed.

## Risks and responses

| Risk | What to do | When and where |
| --- | --- | --- |
| Unreal, caches, and packaged builds may fill the project volume. | Measure free space before, during, and after the first packaged build. Record the engine, cache, intermediate output, and build sizes separately. If space becomes limiting, identify generated files that can be recreated before deciding whether extra storage is needed. | M0. Run the first check in [#2](https://github.com/Hagrid862/GrandTheftAgent/issues/2) and record the project-specific result in [#4](https://github.com/Hagrid862/GrandTheftAgent/issues/4). |
| Codex may need manual help with work inside Unreal Editor. | Try a small change to a Blueprint or level. Save it, reopen the project, and show the result in a packaged build. Record which steps ran independently and who handles any manual steps. | M0. Define permissions in [#5](https://github.com/Hagrid862/GrandTheftAgent/issues/5) and record the trial in [#6](https://github.com/Hagrid862/GrandTheftAgent/issues/6). |
| The open-world scope can expand before the core activity has been tested. | Set the effort limit and define one short session in a small area. Include the mechanics needed to test the chosen activity. Use observed player behavior to decide whether to develop it further, revise it, or try another activity. | M1. Define the session in [#12](https://github.com/Hagrid862/GrandTheftAgent/issues/12) and record playtest results in [#15](https://github.com/Hagrid862/GrandTheftAgent/issues/15). |
| The Mac Studio may hide problems on slower hardware. | Record the hardware, resolution, quality settings, and test route with each measurement. If validation on a lower-spec machine is needed, arrange access before treating the results as evidence for that configuration. | Before M2 measurements. Set the reference configuration in [#16](https://github.com/Hagrid862/GrandTheftAgent/issues/16). |
| A console release could add work before we can test our own build. | Keep the initial build and playtest on macOS. After M2, assess developer access, hardware needs, and packaging effort before committing to PlayStation production work. | Review after M2. Confirm production platforms in [M3.09](https://github.com/Hagrid862/GrandTheftAgent/issues/32). |
| Recurring subscriptions could add cost before they help test the game. | Tie each proposed subscription to a specific deliverable. Confirm the expected cost, the relevant license, and when the subscription can end. | Before any purchase. Review spoken dialogue needs when defining the M2 session or a later production package. |

## Open decisions

| Decision | Owner | When it is needed |
| --- | --- | --- |
| Available review time and the maximum effort to spend on the first prototype | Project owner, with an estimate from Codex | Before approving the M1 session scope |
| Reference hardware and settings for repeatable performance tests | Project owner, with evidence from Codex | Before M2 performance measurements |
| Whether to buy a voice subscription for a particular scene | Project owner | Once the scene and script are approved, before purchase |
| Whether to pursue a PlayStation release | Project owner | Revisit after M2 and settle before committing to PlayStation-specific production work |

Codex gathers evidence, runs the agreed trials, and records outcomes in the relevant issues. The project owner approves the prototype direction, new spending, and release platform choices. Update this document when a result changes one of the assumptions or a decision is made.
