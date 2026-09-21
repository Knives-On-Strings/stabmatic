# Stabmatic Changelog

What changed, in the language of someone playing it rather than building it.

---

## Unreleased

Nothing has shipped yet. This is what the first release will contain, listed
here so testers know what is meant to work. The version number and date land
when it actually goes out.

Hold any note and it plays a stored chord shape, transposed rigidly to that
key — no key awareness, no scale, no substitution.

### Added

- **The Roland MC-909's 64 chord forms**, transcribed from the machine's own
  manual with their names and their quirks intact. Forms 29 to 64 are the
  arpeggio-voiced ones and are marked as such in the display.
- **Capture.** Arm it, play a chord, let go. That shape is now the one under
  your finger — yours immediately, saved or not.
- **Your edits survive a reload.** Close the project with a captured or
  edited chord and it comes back exactly as you left it, whether or not you
  saved it to your library. Loading a different form discards the edit, and
  one undo brings it back.
- **A library of your own with no size limit** — save as new, overwrite,
  rename, delete, and star the ones you reach for.
- **A browser** that filters by chords, arpeggio, your own forms, favourites,
  and by quality: major, minor, seventh, augmented, diminished, suspended.
- **Retrigger and Legato switches.** Retrigger decides whether every note
  re-attacks when you change key — the difference between a stab and a held
  pad. Legato returns you to a key you're still holding when you release a
  later one, the way a mono synth does.
- **A piano-style pad grid** for editing chords by hand, with octave paging
  and live pad lighting during capture.
- **A dot-matrix display with four skins** — stock green, teal, blue OLED and
  amber — showing the current form, whether you've changed it, the arpeggio
  badge, and your host's tempo.
- **Dark and light themes**, and window scaling from half size to double.
- **A first-run note** on routing Stabmatic's MIDI output in your particular
  DAW, because every host does it differently.

### Behaviour worth knowing

- **Velocity and everything else pass straight through** — sustain, pitch
  bend, aftertouch, program change and system exclusive are your synth's
  business, not Stabmatic's. Velocity applies to every note of the chord.
- **One chord at a time.** Overlapping notes in a clip replace each other
  rather than stacking, which keeps a busy MIDI part from turning into a
  wall of notes.
- **No stuck notes.** Every path that stops the plugin, including bypass and
  a panic from the host, releases what it was holding.
- **Stabmatic loads as an instrument**, not a MIDI effect, because Ableton
  Live won't load third-party MIDI-effect plugins at all. Put it before a
  synth and route its MIDI output there.

### Provisional, and said so honestly

Two behaviours are interim choices pending a check against real MC-909
hardware, not guesses about whether the plugin works:

- **What happens when the chord form changes while notes are held** — today,
  the old voicing holds on notes already sounding, and the new form only
  applies to the next note you play.
- **What happens to chord notes that would fall outside MIDI's range** —
  today, they're dropped silently rather than folded or clamped.

### Not in this release, and honestly

- **Windows only.** VST3 and CLAP. macOS and Linux are planned, no date yet.
- **No AU**, on any platform, yet.
- **No Standalone version**, and there will not be one — a MIDI instrument
  has nothing to do outside a host.
- **Reason is not supported**, and can't be — it doesn't let a hosted plugin
  route MIDI out at all.
- **Nothing phones home.** Usage reporting and a bug reporter are not built
  into this release at all — no toggle, nothing to opt out of.
