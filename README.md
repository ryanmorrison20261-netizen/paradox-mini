# Paradox mini

Blank, customizable OS shell (Debian 13 based mini image) with an in-browser layout preview and image downloads.

- `index.html`: blank Paradox desktop shell with layout editor (Alt+L) and "Welcome to Paradox" base settings. Stored only in your browser's localStorage. No CDN, no tracking.
- `vm.html`: lightweight in-browser x86 preview using the v86 emulator and the v86 project's Buildroot test image. **This preview is NOT Paradox itself**; v86 is 32-bit x86 only and cannot boot the Debian image.
- Images: download from the [v0.1-mini release](https://github.com/ryanmorrison20261-netizen/paradox-mini/releases/tag/v0.1-mini). No model, no SSH, no user data inside; root locked, `paradox` account password is set at first login.

## SHA256

| File | sha256 |
|---|---|
| paradox-mini-amd64.qcow2 | `c3f3f804f282de37ed2fcc38360aaf3c2ce8d0825e442a0749b4a5a491175c7d` |
| paradox-mini-arm64.qcow2 | `d29ff95bbaaa10152a22810ce2ba6a3e13994800246a0969f90b7bd52e53e76a` |
| paradox-mini-amd64.qcow2.zst | `a55ec0b617f527b77fe79cb1d4acc72d35c468c8466dcf37bde7e9b01754625b` |
| paradox-mini-arm64.qcow2.zst | `e61da5c32996d613fd9a5248069b3dc401a6dd7b5563d46d719faed1151e308e` |

## Licenses

Paradox web bundle - third-party components (vendored, served locally; no CDN):
- v86 0.5.473 (npm "v86"), BSD-2-Clause: v86/libv86.js, v86/v86.wasm. License: v86/LICENSE-v86-BSD-2-Clause.txt. https://github.com/copy/v86
- SeaBIOS / VGA BIOS binaries from the v86 repo bios/ dir, LGPLv3: v86/seabios.bin, v86/vgabios.bin. License: v86/COPYING-seabios.txt. Source: https://www.seabios.org
- images/buildroot-bzimage68.bin: v86 project's Buildroot Linux test image (Linux kernel + busybox, GPLv2). Fetched from https://i.copy.sh/buildroot-bzimage68.bin. Build config/source: https://github.com/copy/images
Why not the Debian mini image in the browser: v86 emulates a 32-bit x86 CPU (no x86_64), so the amd64 Debian image cannot boot in it.
