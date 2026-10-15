# Stabmatic Changelog

What changed, in the language of someone playing it rather than building it.
Dates are the day the work landed on `main`.

Nothing has been released publicly yet, and no build has been handed to
anyone. 0.2.0 is the first build meant for private testing -- a Windows
installer, not a public release. The first public release will be a beta, for
Windows first.

_Corrected 2026-09-23: this paragraph and the 0.2.0 heading below used to say
0.2.0 was the first build handed to a tester. No Stabmatic build has ever
reached a tester or a user (the owner, 2026-09-23)._

---

## 0.2.26 — built 2026-10-10 — macOS 10.15 and 11 minimum, maker code corrected

0.2.25 was never released; it was an internal step, and nothing in it reached a tester or a user.

### Changed

- **The macOS minimum is lower: macOS 10.15 on an Intel Mac, macOS 11 on an Apple
  Silicon Mac.** It was macOS 15 Sequoia. The installer still refuses anything
  older than that, and now also checks that the plugin inside was built for it.
  (Owner decision O47, 2026-10-08.)
- **Stabmatic now identifies itself to hosts with the company's maker code.**
  Every build up to 0.2.22 carried a one-letter case typo in it, so a host saw
  Stabmatic as coming from a different maker than every other Knives on
  Strings plugin. A host that scanned one of those builds will list this one
  as a new plugin, and a project saved with one will not find it. No such
  build ever left the development machine, so nobody is affected; it is
  corrected now because after the first release it could never be.

### Development

- Stabmatic syncs shared files with the VST Builder boilerplate: a provenance record, a drift check and a
  repo-hygiene step in its gate, and newer hooks and scripts taken from the boilerplate.

---

## 0.2.23 — built 2026-10-09 — report a bug from inside Stabmatic

### Added

- **Report a bug without leaving the plugin.** Open the About box and press
  *Report a bug*. A form opens in your browser with Stabmatic's version, its
  format and your host already filled in, and what you send lands on
  Stabmatic's issue tracker. If the form can't be reached, Stabmatic shows you
  its address so you can copy it instead.
- **You decide whether Stabmatic helps us improve it.** The first time it
  opens, Stabmatic asks once whether it may send anonymous usage data — never
  audio, never MIDI, never anything personal. Say no and no usage data is
  sent. You can change your mind at any time in Settings. Reporting a bug works
  either way.

The changes between 0.2.8 and 0.2.22 — mostly to how Stabmatic looks —
aren't written up here yet.

---

## 0.2.8 — built 2026-09-18 — a real macOS installer

### Added

- **A macOS installer.** A signed, notarized `.pkg` that installs the VST3 and
  the CLAP, lets you pick which, and opens without a Gatekeeper warning. It is
  a universal binary, so it runs natively on both Apple Silicon and Intel Macs.
  Ported from XCent's and Mample's installer, which have shipped this way.
- **Packaging the plugin no longer breaks the plugin.** Signing used to rewrite
  the bundles in the build directory, and the next build invalidated that
  signature, leaving plugins macOS refused to load. Nothing you installed was
  affected -- the packaged copies were always fine -- but a build after a
  packaging run was not.
- **The licence texts now install with the plugin**, to
  `/Library/Application Support/Knives on Strings/Stabmatic/`. The installer's
  licence page said they did; on macOS they only sat inside the disk image
  next to the installer, so anyone who kept just the installer never got them.

### Changed

- **macOS 15 Sequoia is now the minimum.** The installer refuses to run on
  anything older rather than installing a plugin that will not load.

### Fixed

- **The build no longer breaks on a fresh clone on macOS.** Configuring a clean
  checkout failed while copying JUCE's WebView bindings into a directory that
  nothing had created yet.
- **The UI build no longer depends on its own output**, which stalled every
  build after the first one with a dependency cycle.
- **The uninstaller now removes the LV2 build and the standalone app** if an
  earlier release left either behind, and clears their quarantine flags.
- **The README inside the disk image reads properly.** Three arrows in it were
  mangled bytes showing as CJK characters, and its Gatekeeper instructions are
  now only shown when they actually apply.

---

## 0.2.0 — built 2026-09-16 — the first build meant for a tester

_Corrected 2026-09-23: this heading used to say "the first build handed to a
tester". It never was -- no Stabmatic build has reached a tester or a user._

### Added

- **One key in, a full chord out.** Hold any note and Stabmatic plays a stored
  voicing transposed rigidly to it. Move up a semitone and every note moves a
  semitone. It never second-guesses you: no key, no scale, no substitution.
- **The Roland MC-909's 64 chord forms**, transcribed from the manual with
  their names and their quirks intact. Forms 29 to 64 are the arpeggio-voiced
  ones and are marked so in the display.
- **Capture.** Arm it, play a chord, let go. That shape is now the one under
  your finger. It is yours immediately, saved or not.
- **Your edits survive a reload.** Close the project with a captured or edited
  chord and it comes back exactly as you left it, whether or not you saved it
  to the library. Loading a different form discards the edit, and one undo
  brings it back.
- **A library of your own** with no slot limit: save as new, overwrite, rename,
  delete, and star the ones you reach for.
- **A browser** that filters by chords, arpeggio, your own, favourites, and by
  quality: major, minor, seventh, augmented, diminished, suspended.
- **Retrigger and Legato switches.** Retrigger decides whether every note
  re-attacks when you change key, which is the difference between stabs and
  pads. Legato returns you to a key you are still holding when you release a
  later one, the way a mono synth does.
- **A piano-style editor.** Click the keys to build a chord by hand, page the
  window with the octave buttons, and watch the keys light as you capture.
- **A dot-matrix display** with four skins: stock green, teal, blue OLED and
  amber. It shows the form, whether you have modified it, the arpeggio badge
  and the host tempo.
- **Dark and light themes**, and window scaling from half size to double.
- **A first-run note** telling you how to route MIDI out of Stabmatic in your
  particular DAW, because every host does it differently.

### Fixed since 0.1.13

- **The panel was cut off in some hosts.** On a display set above 100 per
  cent, and in hosts that scale plugin windows themselves, the right edge and
  the bottom of the panel fell outside the window: half a button, a sliced
  keyboard. The panel now scales to fit whatever window it is given, the way a
  photograph of a hardware unit keeps its shape. A window larger than the
  panel centres it rather than stretching it.
- **Typing a chord form's name into a host's parameter box picked the wrong
  form**, always the next one up. Type the name of form 1 and you got form 2.
  Hosts that show a parameter as text convert it back and forth, and the
  conversion back was reading the printed number as if it counted from zero.

### Behaviour worth knowing

- **Velocity and everything else pass straight through.** Sustain, pitch bend,
  aftertouch, program change and system exclusive are your synth's business,
  not ours. Velocity applies to every note of the chord.
- **One chord at a time.** Overlapping notes in a clip replace each other
  rather than stacking, which is what the hardware does and what keeps a busy
  MIDI part from turning into a wall.
- **No stuck notes.** Every path that stops the plugin, including bypass and a
  panic from the host, releases what it was holding.
- **Stabmatic loads as an instrument**, not a MIDI effect, because Ableton Live
  will not load third-party MIDI-effect plugins at all. You put it before a
  synth and route its MIDI output there.

### Not yet, and honestly

- **Reason is not supported.** It cannot route MIDI out of a plugin, so there
  is nothing to do about it from this end.
- **No AU on macOS yet.** macOS gets VST3 and CLAP. AU waits until the format
  question can be tested on an actual Mac rather than guessed at.
- **There is no standalone version** and there will not be one. A MIDI
  instrument has nothing to do outside a host.
- **Two behaviours are provisional** until they can be checked against real
  MC-909 hardware: what happens when the chord form changes while notes are
  held, and what happens to chord notes that fall off the end of the MIDI
  range. Today they hold, and they are dropped, respectively.
- **Nothing phones home in current builds.** The usage reporting and the bug
  reporter are compiled out entirely, so there is no toggle to find and no
  request to block. If that changes, it will be opt-in, it will be anonymous,
  and it will never include your audio, your MIDI or anything about you.
