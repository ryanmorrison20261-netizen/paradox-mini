# Paradox mini documentation

This folder captures the current project snapshot and supporting system information for the repository.

## Repository overview

- Repository: `ryanmorrison20261-netizen/paradox-mini`
- Description: `Paradox mini: blank customizable OS shell, in-browser preview and downloads`
- Primary language: HTML (100%)
- Project type: static browser-based interface with downloadable VM images and embedded preview tooling

## System context

This is a lightweight, browser-hosted desktop shell project with a minimal static web footprint:

- `index.html` provides the main Paradox desktop shell and the layout editor.
- `vm.html` provides an in-browser x86 preview backed by the `v86` emulator.
- `v86/` stores the vendored emulator assets and BIOS files.
- `downloads/` contains packaged disk/image artifacts for distribution.
- `images/` stores static project images.

## Operational notes

- The application is intentionally browser-focused and stores user configuration in `localStorage` rather than a remote backend.
- The preview feature is not a full Paradox OS runtime; it uses the v86 emulator and a Buildroot-based test image.
- The repo explicitly states that the preview is limited by the emulator architecture: v86 is 32-bit x86 only, so the x86_64 Debian image cannot boot in that environment.
- Distribution images are published as downloadable qcow2 and zstd-compressed variants for amd64 and arm64 targets.

## Security and integrity

The README includes SHA256 hashes for the repository's distribution images. These should be verified before deployment or trust decisions:

- `paradox-mini-amd64.qcow2`
- `paradox-mini-arm64.qcow2`
- `paradox-mini-amd64.qcow2.zst`
- `paradox-mini-arm64.qcow2.zst`

## Key files

- `README.md` – project description, usage notes, and distribution information.
- `index.html` – blank desktop shell and custom layout editor.
- `vm.html` – browser preview harness for the emulator.
- `NOTICE.txt` – repository notice and licensing context.

## PoC / project position

This repository reads as a proof-of-concept and distribution package for a customizable browser-based shell environment. It is intentionally self-contained and avoids third-party CDN dependencies for its core browser bundle.

The project combines:

1. a static front-end shell,
2. an embedded VM preview,
3. downloadable OS images,
4. local-only configuration handling.

This makes it suitable for a lightweight demonstration environment, desktop shell prototyping, and image-based preview workflows without remote service dependencies.
