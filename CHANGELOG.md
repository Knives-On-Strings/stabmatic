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

_Corrected 2026-10-26: that stopped being true in October. macOS betas have
been shared with testers through the Knives on Strings "Stabmatic-beta" Drive
folder since then: 0.2.22 (placed there 2026-10-07), 0.2.23 (2026-10-09),
0.2.31 and 0.2.34 (2026-10-28). Still nothing public._

---

## 0.2.36 — built 2026-11-02 — Stabmatic tells you when there's an update

0.2.35 was an internal step; it never reached a tester. Playing is
unchanged from 0.2.34.

### UI

- **New:** **A red dot on the About button means a newer version is out.** Open
  About and it names the new version beside yours, with a link to what
  changed. Nothing pops up and nothing interrupts you.
- **New:** **You choose how often Stabmatic looks.** Settings has a new Updates
  section: Daily, Weekly (the default), Monthly or Never. **Check now**
  looks straight away, and the section shows when it last checked.
  A check asks the Knives on Strings server for Stabmatic's latest
  version number, and that's all it sends: nothing about you, your
  computer or your music.
- **New:** **This is a beta, so it hears about newer betas** as well as full
  releases.

### Maintenance

- **Built on JUCE 9.0.4**, the newest version of the framework Stabmatic
  is built with, which brings its fixes along.

---

## 0.2.34 — built 2026-10-28 — a new download name

0.2.32 and 0.2.33 were internal steps; neither reached a tester. On a Mac,
0.2.34 plays exactly like 0.2.31.

### Hosts & formats

- **Improved:** **The download has a new name:** `Stabmatic-0.2.34-macos-universal.dmg`.
  "Universal" means one download covers Intel and Apple Silicon Macs, as
  before. Every Knives on Strings plugin is moving to this naming:
  product, version, system, then the kind of computer it runs on.

---

## 0.2.31 — built 2026-10-26 — the Mac window opens properly

0.2.24 to 0.2.30 were internal steps; none of them reached a tester. This
entry covers everything since the 0.2.23 beta that you will notice.

### UI

- **Fixed:** **The window no longer opens blank on a Mac.** In some hosts, most often
  Ableton Live, Stabmatic's window could open as an empty dark grey box and
  stay that way until you resized it, or closed and reopened it. It now opens
  with its controls every time. (The interface was created after the window
  had been sized, so it was never given a size of its own.)

### Hosts & formats

- **Improved:** **Runs on older Macs**: macOS 10.15 Catalina on an Intel Mac, macOS 11 Big
  Sur on Apple Silicon (from 0.2.26, below).
- **Fixed:** **Stabmatic looks like a new plugin to your DAW if you had a 0.2.22 or
  0.2.23 beta.** The maker code correction described under 0.2.26 below
  reaches testers in this release. Your DAW lists Stabmatic as new, and
  projects saved with those betas report it as missing: add it to the track
  again. The settings that copy held in the project don't carry over. This
  happens once.

---

## 0.2.26 — built 2026-10-10 — macOS 10.15 and 11 minimum, maker code corrected

0.2.25 was never released; it was an internal step, and nothing in it reached a tester or a user.

### Hosts & formats

- **Improved:** **The macOS minimum is lower: macOS 10.15 on an Intel Mac, macOS 11 on an Apple
  Silicon Mac.** It was macOS 15 Sequoia. The installer still refuses anything
  older than that, and now also checks that the plugin inside was built for it.
  (Owner decision O47, 2026-10-08.)
- **Fixed:** **Stabmatic now identifies itself to hosts with the company's maker code.**
  Every build up to 0.2.22 carried a one-letter case typo in it, so a host saw
  Stabmatic as coming from a different maker than every other Knives on
  Strings plugin. A host that scanned one of those builds will list this one
  as a new plugin, and a project saved with one will not find it. It is
  corrected now because after the first release it could never be.
  _Corrected 2026-10-26: this entry said the typo was only in builds up to
  0.2.22 and that "no such build ever left the development machine, so nobody
  is affected". Both are wrong. The 0.2.22 and 0.2.23 macOS betas in the
  Stabmatic-beta folder carry it (0.2.23's installer, read 2026-10-26:
  VST3 class ID `...4B6E6F73...`, "Knos"; 0.2.31's: `...4B6E6F53...`,
  "KnoS"), so their testers are affected. The 0.2.31 entry above tells them._
## 0.2.23 — built 2026-10-09 — report a bug from inside Stabmatic

The changes between 0.2.8 and 0.2.22 — mostly to how Stabmatic looks —
aren't written up here yet.

### UI

- **New:** **Report a bug without leaving the plugin.** Open the About box and press
  *Report a bug*. A form opens in your browser with Stabmatic's version, its
  format and your host already filled in, and what you send lands on
  Stabmatic's issue tracker. If the form can't be reached, Stabmatic shows you
  its address so you can copy it instead.
- **New:** **You decide whether Stabmatic helps us improve it.** The first time it
  opens, Stabmatic asks once whether it may send anonymous usage data — never
  audio, never MIDI, never anything personal. Say no and no usage data is
  sent. You can change your mind at any time in Settings. Reporting a bug works
  either way.

---

## 0.2.8 — built 2026-09-18 — a real macOS installer

### Hosts & formats

- **New:** **A macOS installer.** A signed, notarized `.pkg` that installs the VST3 and
  the CLAP, lets you pick which, and opens without a Gatekeeper warning. It is
  a universal binary, so it runs natively on both Apple Silicon and Intel Macs.
  Ported from XCent's and Mample's installer, which have shipped this way.
- **Improved:** **macOS 15 Sequoia is now the minimum.** The installer refuses to run on
  anything older rather than installing a plugin that will not load.
- **Fixed:** **The licence texts now install with the plugin**, to
  `/Library/Application Support/Knives on Strings/Stabmatic/`. The installer's
  licence page said they did; on macOS they only sat inside the disk image
  next to the installer, so anyone who kept just the installer never got them.
- **Fixed:** **The uninstaller now removes the LV2 build and the standalone app** if an
  earlier release left either behind, and clears their quarantine flags.
- **Fixed:** **The README inside the disk image reads properly.** Three arrows in it were
  mangled bytes showing as CJK characters, and its Gatekeeper instructions are
  now only shown when they actually apply.
## 0.2.0 — built 2026-09-16 — the first build meant for a tester

_Corrected 2026-09-23: this heading used to say "the first build handed to a
tester". It never was -- no Stabmatic build has reached a tester or a user._

**Not yet, and honestly.**

**Reason is not supported.** It cannot route MIDI out of a plugin, so there
is nothing to do about it from this end.

**No AU on macOS yet.** macOS gets VST3 and CLAP. AU waits until the format
question can be tested on an actual Mac rather than guessed at.

**There is no standalone version** and there will not be one. A MIDI
instrument has nothing to do outside a host.

**Two behaviours are provisional** until they can be checked against real
MC-909 hardware: what happens when the chord form changes while notes are
held, and what happens to chord notes that fall off the end of the MIDI
range. Today they hold, and they are dropped, respectively.

**Nothing phones home in current builds.** The usage reporting and the bug
reporter are compiled out entirely, so there is no toggle to find and no
request to block. If that changes, it will be opt-in, it will be anonymous,
and it will never include your audio, your MIDI or anything about you.

### Chords

- **New:** **One key in, a full chord out.** Hold any note and Stabmatic plays a stored
  voicing transposed rigidly to it. Move up a semitone and every note moves a
  semitone. It never second-guesses you: no key, no scale, no substitution.
- **New:** **The Roland MC-909's 64 chord forms**, transcribed from the manual with
  their names and their quirks intact. Forms 29 to 64 are the arpeggio-voiced
  ones and are marked so in the display.
- **New:** **Retrigger and Legato switches.** Retrigger decides whether every note
  re-attacks when you change key, which is the difference between stabs and
  pads. Legato returns you to a key you are still holding when you release a
  later one, the way a mono synth does.
- **New:** **Velocity and everything else pass straight through.** Sustain, pitch bend,
  aftertouch, program change and system exclusive are your synth's business,
  not ours. Velocity applies to every note of the chord.
- **New:** **One chord at a time.** Overlapping notes in a clip replace each other
  rather than stacking, which is what the hardware does and what keeps a busy
  MIDI part from turning into a wall.
- **New:** **No stuck notes.** Every path that stops the plugin, including bypass and a
  panic from the host, releases what it was holding.

### Capture

- **New:** **Capture.** Arm it, play a chord, let go. That shape is now the one under
  your finger. It is yours immediately, saved or not.
- **New:** **Your edits survive a reload.** Close the project with a captured or edited
  chord and it comes back exactly as you left it, whether or not you saved it
  to the library. Loading a different form discards the edit, and one undo
  brings it back.
- **New:** **A piano-style editor.** Click the keys to build a chord by hand, page the
  window with the octave buttons, and watch the keys light as you capture.

### Browser

- **New:** **A library of your own** with no slot limit: save as new, overwrite, rename,
  delete, and star the ones you reach for.
- **New:** **A browser** that filters by chords, arpeggio, your own, favourites, and by
  quality: major, minor, seventh, augmented, diminished, suspended.

### UI

- **New:** **Dark and light themes**, and window scaling from half size to double.
- **New:** **A first-run note** telling you how to route MIDI out of Stabmatic in your
  particular DAW, because every host does it differently.
- **Fixed:** **The panel was cut off in some hosts.** On a display set above 100 per
  cent, and in hosts that scale plugin windows themselves, the right edge and
  the bottom of the panel fell outside the window: half a button, a sliced
  keyboard. The panel now scales to fit whatever window it is given, the way a
  photograph of a hardware unit keeps its shape. A window larger than the
  panel centres it rather than stretching it.

### Skins

- **New:** **A dot-matrix display** with four skins: stock green, teal, blue OLED and
  amber. It shows the form, whether you have modified it, the arpeggio badge
  and the host tempo.

### Hosts & formats

- **New:** **Stabmatic loads as an instrument**, not a MIDI effect, because Ableton Live
  will not load third-party MIDI-effect plugins at all. You put it before a
  synth and route its MIDI output there.
- **Fixed:** **Typing a chord form's name into a host's parameter box picked the wrong
  form**, always the next one up. Type the name of form 1 and you got form 2.
  Hosts that show a parameter as text convert it back and forth, and the
  conversion back was reading the printed number as if it counted from zero.
