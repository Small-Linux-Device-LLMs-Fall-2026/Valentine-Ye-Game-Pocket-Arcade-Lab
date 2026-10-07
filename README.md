# Valentine-Ye-Game-Pocket-Arcade-Lab
# GoF2 Pocket

Porting the open-source *Galaxy on Fire 2* remake to a Raspberry Pi 5, and building
it into a single-game handheld with a 3D-printed shell.

**Status:** concept → proposal → prototype → working → released

## Why this game

Galaxy on Fire 2 (FISHLABS, 2010) is a single-player space shooter. I have played it
since 2019; when anyone asks what game I like, this is the answer. The course asked
me to choose between building a platform for many games and devoting a semester to
one game I love. This is the second kind.

## What exists already

[JoppieToppie/Galaxy-on-Fire-2-Unity-Remake](https://github.com/JoppieToppie/Galaxy-on-Fire-2-Unity-Remake)
is a Unity 6 remake built from the decompiled original code and the original assets.
The full campaign and both add-ons are playable; controllers are supported. It ships
builds for Windows, Android and Linux x86_64 — **not for ARM64 Linux**, which is what
a Raspberry Pi 5 runs. That gap is this project.

## What this project does (planned)

1. Build the remake for aarch64 Linux and get it running on a Pi 5.
2. Make it feel like a handheld: boots straight into the game, controller mapped,
   screen and performance tuned for the Pi's GPU.
3. A shell designed in Fusion 360 and printed on my own 3D printers.

## Minimum viable product

The remake's main menu renders on the Pi 5. Then: one mission playable with a
controller at a tolerable frame rate.

## Risks, named up front

- **Unity on ARM64 Linux.** This is the unknown. If a native Linux ARM64 build does
  not work, the fallback is running Android on the Pi 5 and installing the remake's
  Android APK. Either way the device is a Pi 5 and the game is this one.
- **Performance.** The remake uses Unity's URP; the Pi 5's GPU is modest. Expect a
  lot of tuning — resolution, effects, frame caps. That tuning is where the AI
  co-development happens.
- **Rights.** The remake is a fan project built on FISHLABS's assets. This repo will
  never redistribute game assets; it holds only my build scripts, configs, shell
  files and notes. The ethics of decompiling and preserving a game its publisher no
  longer maintains is a topic I intend to write about honestly, since this course
  asks for it.

## Hardware

- Raspberry Pi 5 (16 GB), aarch64
- Display and controller: to be chosen (tracked in Issues)
- Shell: 3D-printed, Handmade refined (FDM 3D Printing, Stereolithography Resin Printing)

## Development setup

- Cloud node: Azure, Ubuntu Server 24.04 Arm64, `Standard_B4pls_v2` (4 vCPU, 8 GB),
  on Tailscale. Oracle Free Tier rejected my sign-up; Azure for Students was the
  fallback, and its region and quota restrictions took one long night to work
  around — documented in `docs/azure-node-notes.md`.
- Node and device are both aarch64, so what builds on the node runs on the Pi.

## Models

Co-authored with AI models, attributed per the course's
[ATTRIBUTION.md](https://github.com/mfadt/sld-fall-2026/blob/main/ATTRIBUTION.md):

- **Claude Fable 5.1** (Anthropic) — planning, build scripts, documentation
- **gemma4:e4b** via Ollama, self-hosted on the cloud node — local coding assistant
  from Week 11

Every commit a model contributed to carries a `Co-Authored-By:` trailer.

## Precedents

- [Galaxy-on-Fire-2-Unity-Remake](https://github.com/JoppieToppie/Galaxy-on-Fire-2-Unity-Remake) — the thing being ported
- [ETK, the Emulation Tuning Kit](https://github.com/mercurious/etk) — the course case study: build on the node, deploy to a handheld
- [RetroPie](https://retropie.org.uk/) — the platform route I decided not to take

## Known behaviour

Nothing runs yet. This README is the proposal.

## Transcripts

Links to working transcripts will be added at each milestone.

## License

To be chosen in the Week 4 discussion. Leaning MIT for my own files; the remake and
the game keep their own terms.
