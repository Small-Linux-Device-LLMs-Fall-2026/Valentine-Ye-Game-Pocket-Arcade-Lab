# Valentine-Ye-Game-Pocket-Arcade-Lab
# Pocket Arcade Lab

A handheld emulation console built on a Raspberry Pi 5, with a small language
model that helps tune emulator settings — and a 3D-printed shell designed and
printed at home.

**Status:** concept → proposal → prototype → working → released

## Why

Emulator configuration is manual labor: every game needs its own resolution,
frame-rate and input settings, and the answers live in forum threads. At the same
time, I work as a research assistant in the Parsons Retrocomputing Lab, restoring a
SEGA NAOMI arcade board. I want a pocket-sized way to study how games from that era
behave on original hardware versus under emulation.

## What it does (planned)

1. Runs an emulator front end on a Raspberry Pi 5 with a screen and a game controller.
2. Reads the emulator's run logs and asks a small local model for tuning suggestions
   (resolution, frame skip, input mapping) — the "tuning" part of an Emulation
   Tuning Kit, handed to an AI.
3. Lives in a shell I design in Fusion 360 and print on my own FDM printers.

## Minimum viable product

- Pi 5 boots into one emulator and plays one game. That's it.
- Then: one Python script that reads a log file and prints a tuning suggestion.

## Hardware

- Raspberry Pi 5 (8 GB), aarch64
- Display and controller: to be chosen (see Issues)
- Shell: 3D-printed, FDM

## Development setup

- Cloud node: Azure, Ubuntu Server 24.04 Arm64, `Standard_B4pls_v2` (4 vCPU, 8 GB),
  connected over Tailscale. (Oracle Free Tier rejected my sign-up; Azure for Students
  was the fallback — the region and quota restrictions that took one long night are
  documented in `docs/azure-node-notes.md`.)
- Device and node are both aarch64, so builds on the node run on the Pi.

## Models

This project is co-authored with AI models, attributed per the course's
[ATTRIBUTION.md](https://github.com/mfadt/sld-fall-2026/blob/main/ATTRIBUTION.md):

- **Claude Fable 5.1** (Anthropic) — planning, code, documentation
- **gemma4:e4b** via Ollama, self-hosted on the cloud node — local inference for the
  tuning assistant (Week 11 onward)

Every commit a model contributed to carries a `Co-Authored-By:` trailer.

## Precedents

- [RetroPie](https://retropie.org.uk/) — the baseline this project starts from
- [ETK, the Emulation Tuning Kit](https://github.com/mercurious/etk) — the course case study

## Known behaviour

Nothing runs yet. This README is the proposal.

## Transcripts

Links to working transcripts will be added at each milestone.

## License

To be chosen in Week 4 discussion. Leaning MIT.
