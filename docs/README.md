# Paradox mini documentation

This folder documents the project in a neutral, reusable way without embedding personal account or email identifiers in the source content.

## Project overview

- Project: `Paradox mini`
- Type: browser-hosted desktop shell prototype with downloadable VM images and an in-browser preview
- Primary language: HTML (100%)
- Deployment model: static front-end files plus packaged VM artifacts

## System context

This project is intentionally lightweight and self-contained:

- `index.html` provides the main desktop shell and layout editor.
- `vm.html` provides the in-browser x86 preview using the `v86` emulator.
- `v86/` stores the bundled emulator runtime and BIOS files.
- `downloads/` contains packaged disk image artifacts for distribution.
- `images/` stores static project assets and screenshots.

## Multi-bot system concept

To support a stronger operational model, the repository can be framed around a single coordinating bot and four supporting specialist bots that share the workload and connect together to make the overall system more complete.

### Brian Grok Bot

`Brian Grok Bot` acts as the central orchestrator and command layer. It coordinates the overall system direction, keeps the project aligned with the target state, and routes decisions to the right supporting workers.

### Supporting bots

1. `Ops Bot` — handles runtime health, deployment checks, and system stability.
2. `Research Bot` — gathers requirements, technical notes, and architecture context.
3. `Build Bot` — manages code changes, validation, and automation flow.
4. `QA Bot` — verifies quality, alerts, edge cases, and final readiness.

Together, these bots form a linked operational system where each bot carries a defined share of the load while the primary orchestrator keeps the system coherent and aligned.

This model is especially suitable for a lightweight project workflow where the central bot provides direction and the supporting bots handle the heavy lifting in parallel.

## Operational notes

- The app stores layout and settings in the browser via `localStorage` rather than a remote database.
- The preview is an emulator-based demonstration and is not the full Paradox OS runtime.
- The project intentionally avoids CDN dependencies for the core browser bundle.
- The repo distributes qcow2 and zstd-compressed disk images for amd64 and arm64 targets.

## Security review

The checked source files do not contain any obvious hardcoded API keys, tokens, passwords, or personal email addresses.

Recommended practice:

- Keep secrets out of frontend code and generated HTML.
- Use environment variables or secure secret stores for any future backend features.
- Verify SHA256 values before trusting downloaded VM images.

## Key files

- `README.md` – project description, usage notes, and image distribution information.
- `index.html` – blank desktop shell and layout editor.
- `vm.html` – browser preview harness for the emulator.
- `NOTICE.txt` – licensing and provenance notice.

## PoC / project positioning

This repository is best understood as a proof-of-concept desktop-shell experiment and demonstration bundle. It combines a static front-end interface, an embedded virtual machine preview, and downloadable OS images in a single, self-contained package.

This makes it suitable for lightweight prototyping, local customization experiments, and browser-driven preview workflows without requiring a remote service backend.

## Important note

Git author metadata (for example, commit email addresses) is part of Git history and not usually stored inside repository source files themselves. If you want the repository history scrubbed, that must be done with a repository rewrite or a fresh branch history, not by editing the current source files alone.
