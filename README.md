# Stabmatic

**One key in, a full chord out** — Roland's Chord Memory function as a plugin.

> **Not released yet.** Stabmatic is still in development. This repo is open
> ahead of release so testers have somewhere to report bugs — there is nothing
> to download here, and no version to install unless you were handed a build
> directly.

- **Formats:** VST3, CLAP
- **Platforms:** Windows first. macOS has been built, and its installer is
  written — universal, signed and notarized — but the platform has not been
  through a release check, so it is not promised for the first release.
  Linux (VST3 + LV2) after that.
- **Status:** In development, pre-release

## Links

- [Product page](https://knivesonstrings.com/stabmatic)
- [Manual](https://knivesonstrings.com/stabmatic/manual)
- [Gumroad](https://knivesonstrings.gumroad.com/l/stabmatic) — where it will be published

<!-- KVR link goes here once Stabmatic is listed: [Check it out on KVR](https://www.kvraudio.com/product/stabmatic-by-knives-on-strings) -->

## What it is

A chord form is a set of semitone offsets. Whatever note you play, the whole
form transposes rigidly to it — no key awareness, no scale quantising, no
chord substitution. Stabmatic combines Roland's two Chord Memory approaches:
**capture** (play a chord, release, it's learned — Alpha Juno / MKS-50
style) and a **library** (the MC-909's 64 factory chord forms, transcribed
verbatim, plus your own unlimited library and a pad-grid editor).

Stabmatic is a MIDI instrument — MIDI in, MIDI out, no sound of its own. You
put it before a synth and route its MIDI output there; the manual has the
recipe for every major host. It doesn't work in Reason, which can't route
MIDI out of a hosted plugin at all.

Roland, MC-909, Alpha Juno and MKS-50 are trademarks of Roland Corporation.
Stabmatic is an independent project and is not affiliated with, endorsed by,
or sponsored by Roland Corporation.

## Support

This repo is for **bug reports** and **feature requests** only — no source code is hosted here.

- [Report a bug](https://github.com/Knives-On-Strings/stabmatic/issues/new?template=bug.yml)
- [Request a feature](https://github.com/Knives-On-Strings/stabmatic/issues/new?template=feature.yml)
- Email: knivesonstrings@gmail.com

## About

Stabmatic is built by [Knives on Strings](https://knivesonstrings.com), a garage-based engineering team building audio plugins, browser extensions, and other things that probably work.
