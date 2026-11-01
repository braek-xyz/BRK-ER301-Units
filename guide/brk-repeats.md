# BRK Repeats: beat repeater

BRK Repeats is the REPEAT + FREEZE effect from the BRAEK plug-in LAZERS. It keeps a short memory of the incoming sound
and **plays a slice of it back over and over**, locked to your tempo. On top of that it can randomly skip and jump
(`braek`), wobble the speed or play backwards (`wonk`), and crush the sound (`dmg`). Use it for stutters, glitch
rolls, beat-repeat fills and broken loops.

- Effect, stereo in / out (also works in mono chains)
- Syncs to a clock, or runs in free time
- Freeze holds a slice and loops it
- Longest cycle: 4 seconds

New to the BRK units? Read [Getting started](getting-started.md) first: it explains the knobs, the gates, the clock
and why `mix` starts at 0.

## Quick start

1. Put BRK Repeats after a drum loop or other rhythmic sound.
2. Turn **`mix`** to 1. With the defaults you hear the sound almost unchanged: one slice per cycle is just the live
   sound.
3. Turn **`rpts`** up to 4. Now each half bar (the default `time`) is cut into 4 slices and one of them repeats.
4. Move **`pos`** to choose which slice repeats.
5. Add a little **`braek`** and **`wonk`** for random variations, and press **`frz`** to lock the current loop.

## The controls

Controls appear in this order on screen.

| On screen | Range (default) | What it does |
|---|---|---|
| `mix` | 0 to 1 (0) | Balance of incoming sound and repeats. 0 = dry only, 1 = repeats only. |
| `time` | note lengths or time (1/2) | **Length of one cycle**: the stretch of time that gets sliced. Synced: 1/16 to 2 bars, shown by name. Free (`free` on): 12.5 ms to 4 s (0.5 = about 224 ms). |
| `rpts` | 1 to 16 (1) | **Repeats**: how many slices each cycle is cut into. The chosen slice plays that many times to fill the cycle. 1 = no slicing. Higher = faster, shorter stutters. |
| `pos` | 0 to 1 (0) | **Position**: which slice of the cycle is repeated. 0 = the first slice, 1 = the last. |
| `braek` | 0 to 1 (0) | **Random gaps and jumps.** Repeats are randomly dropped to silence or jump to other slices. More = more broken. |
| `wonk` | 0 to 1 (0) | **Random speed and direction** for each repeat: reverse, half speed, double speed... More = wilder. |
| `dmg` | 0 to 1 (0) | **Damage**: lowers the sample rate and bit depth of the repeats for a lo-fi, crunchy sound. The dry sound is not affected. |
| `frz` | toggle (off) | **Freeze**: holds the current cycle and loops it. Starts and stops cleanly at the end of a cycle, so it stays in time. |
| `hold` | momentary | **Freeze only while held.** Starts and stops immediately, for stabs and fills. |
| `free` | toggle (off) | Off = `time` follows the clock (note lengths). On = `time` is free in milliseconds. |
| `clock` | gate input | Clock pulses, one per beat. No clock = 120 BPM. |
| `div` | 1 to 32 (1) | Clock divider: how many incoming pulses make one beat (4 for a 16th-note clock, 24 for 24 PPQN). |

## How the controls work together

- **`time` ÷ `rpts` = the length of one repeat.** `time` 1/2 with `rpts` 4 repeats an 1/8 note; with `rpts` 8 a
  1/16 note; with `rpts` 16 a 1/32 note (a fast roll).
- **`rpts` 1 with no `braek` or `wonk` is the live sound.** That makes a good "off" position: you can turn `rpts`
  up and down (by hand or CV) to bring stutters in and out without touching `mix`.
- **Freeze and `mix`**: if you freeze while `mix` is at 0, `mix` jumps to fully wet so you hear the frozen loop
  (the same as in LAZERS).
- **`frz` vs `hold`**: `frz` waits for the end of the cycle (tight, musical); `hold` reacts at once (good for
  performance and for gates from a sequencer).

## Patch ideas

- **Beat-repeat fill:** synced, `time` 1/2, `rpts` 8, `mix` 1. Patch a gate into `hold` on the last beat of every
  4 bars for a classic stutter fill.
- **Glitch drums:** `rpts` 4, `braek` 0.4, `wonk` 0.3, `dmg` 0.2. Different every bar.
- **Wonky loop:** `rpts` 2, `wonk` 0.8 with `frz` on. Each repeat plays at half speed, double speed or in reverse.
- **Roll that speeds up:** a rising envelope or LFO on `rpts` from 1 to 16.
- **Choose the slice from a sequencer:** CV into `pos` picks a different slice on every step.
- **Lo-fi loop:** `frz` on, `dmg` 0.7, `mix` 1. A crunchy frozen loop to play over.

## CPU

About 16 % on the ER-301 in normal use. It costs most with `hold` being switched very fast by an audio-rate or very
fast gate.
