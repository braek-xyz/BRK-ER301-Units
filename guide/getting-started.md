# Getting started with the BRK units

New to adding units on the ER-301? This page covers the basics that all three BRK units share.
Then read the page for the unit you want: [BRK Tapz](brk-tapz.md), [BRK Repeats](brk-repeats.md), [BRK Lazers](brk-lazers.md).

## Adding a unit

1. Install the packages and **restart the ER-301** (see the [README](../README.md#install)).
2. Open a channel (OUT1, OUT2 ...) and insert a unit as you would any other.
3. In the unit list, open the **BRAEK** category and pick **BRK Tapz**, **BRK Repeats** or **BRK Lazers**.

Where to put it:

- **BRK Tapz and BRK Repeats are effects.** Put them *after* a sound: for example after an input unit (IN1),
  a sample player or an oscillator. They work in stereo and mono chains.
- **BRK Lazers is a sound source.** Put it in an **empty** chain or at the start of one. It ignores whatever comes
  into the chain and plays its own sound when it gets a trigger.

## The two kinds of control

Every control on these units is one of two standard ER-301 types, so they work like the built-in units.

**Knobs (faders).** Select the control and turn the encoder to set it. Hold the fine/coarse button as usual for
small steps. Like every ER-301 fader, each one can also be moved by CV: open the control's modulation chain and put a
source in it (an input such as IN2, an LFO, an envelope, a sequencer unit...). The fader sets the starting point
and the modulation adds to it.

**Gates (buttons): `frz`, `hold`, `free`, `clock`, `trig`, `rand`.** These react to a gate or trigger signal.
- To press one by hand: select it and use its **fire** button (the third sub-button). That is the quickest way to
  try them out.
- To drive one from a patch cable or another unit: open the control's modulation chain and put a gate source in it,
  for example a gate input (G1-G4) or the ER-301's own clock or trigger units.
- Some gates **toggle** (each pulse switches on / off): `frz`, `free`, `rand`.
  `hold` is **momentary**: on while the gate is high, off when it drops.
  `clock` and `trig` count **pulses** (rising edges).

## Clock and sync (BRK Tapz and BRK Repeats)

Both effects can lock their timing to a clock:

- `free` **off** (the default) = **synced**. The time knob (`len` on Tapz, `time` on Repeats) steps through note
  lengths and shows them by name: 1/16, 1/8, 1/8d, 1/4, 1/4d, 1/2, 1/2d, 1bar, 1.5bar, 2bar (d = dotted).
- `free` **on** = **free time**. The same knob sets a time in milliseconds, with no clock needed.
- Patch your clock into `clock`, one pulse per beat (quarter note). With **no clock**, the units run at **120 BPM**.
- If your clock sends more than one pulse per beat, set `div` to that number: 2 = every 2nd pulse is a beat,
  4 for 16th-note clocks, 24 for 24 PPQN. Clocks from 10 to 4000 pulses a minute are accepted.

## Mix starts at zero

Both effects start with `mix` at **0** (fully dry), so the unit makes **no change** to the sound until you
turn `mix` up. This is on purpose, so you can add them to a patch without a sudden jump. If you hear nothing
happening, turn `mix` up first.

## CPU tips

- Rough CPU on the ER-301: BRK Tapz about 8 %, BRK Repeats about 16 %, BRK Lazers about 20 % for single hits and up
  to about 68 % with `poly` 8 and long tails. Lower `poly` and shorter `dec` / `tail` use less.
- On the ER-301, **bypassing a unit does not stop it using CPU**, unless you set
  *Settings > Units > "Does bypassing a unit also disable it?"* to **yes**.
- If the ER-301 runs out of CPU, the sound breaks up into short stuttering bits (it can sound like a stuck freeze).
  Watch the CPU % when you stack several units.

## Updating to a new version

Delete the old `.pkg` files from `ER-301/packages`, copy in the new ones, install them, and **restart the ER-301**.
Until a restart the ER-301 keeps the old version loaded, and the unit can misbehave (for example the note names
disappear).
